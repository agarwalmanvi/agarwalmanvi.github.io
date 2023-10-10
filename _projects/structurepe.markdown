---
layout: page
title: structure-informed positional encoding
description:
img:
importance: 1
---

<script src="https://cdn.jsdelivr.net/combine/npm/tone@14.7.58,npm/@magenta/music@1.23.1/es6/core.js,npm/focus-visible@5,npm/html-midi-player@1.5.0"></script>


This is the companion website to our ICASSP 2024 submission: 
_Structure-informed Positional Encoding for Music Generation_.

# Contents

1. [Generated Samples](#generated-samples)
   1. [Next-timestep Prediction](#next-timestep-prediction)
   2. [Accompaniment Generation](#accompaniment-generation)
2. [Dataset Supplement](#dataset-supplement)
3. [Training Details](#training-details)

# Generated Samples

Below, we give some good and bad examples of both the baseline methods and our proposed methods. The abbreviations are as follows:
1. Baselines
   1. <code>NoPE</code>: No Positional Encoding
   2. `APE`: Absolute Positional Encoding
   3. `RPE`: Relative Positional Encoding
   4. `S-APE/b`: SymphonyNet
   5. `S-RPE/b`: RIPO Attention
2. Our Methods
   1. `L S-APE`: StructureAPE with learnable embedding
   2. `S S-APE`: StructureAPE with sinusoidal embedding
   3. `L S-RPE`: StructureRPE with learnable embedding
   4. `S S-RPE`: StructureRPE with sinusoidal embedding
   5. `NS-RPE/c`: StructureRPE with nonstationary kernel on chord labels
   6. `NS-RPE/s`: StructureRPE with nonstationary kernel on section labels

We only use the sinusoidal embedding with the `NS-*` variants because of constraints on computational capacity.

## Next-timestep Prediction

[Good examples :link:](../spe/next_ts/good)

[Not-So-Good examples :link:](../spe/next_ts/not_so_good)

## Accompaniment Generation

[Good examples :link:](../spe/acc_gen/good)

[Not-So-Good examples :link:](../spe/acc_gen/not_so_good)

# Dataset Supplement

The dataset we use is the Chinese POP909 dataset, which comes with structural annotations. 
The MIDI songs are cleanly divided into three tracks: melody, bridge and piano. We first convert them into pianorolls.
We select only those songs with a 4/4 time signature and that are long enough to provide at least one sample, giving us a total of 866 songs.

The structural labels contain four categories for each timestep, with each category corresponding to a different temporal resolution: 
tempo, section, chord and melody. 
However, these annotations are not properly aligned with the MIDI file due to two sources of variable-length error:
1. silence at the beginning of the song
2. musical phrases that are not included in the labeling, such as pickup measures

Although the first source of error is trivial to eliminate, the second cannot be corrected with high precision in an automated fashion. 
Hence, I manually select the beat position at which the structural annotations should start for each song.
Below, I show the validation loss for a selection of baselines and proposed methods, using 20% of the dataset.

Insert a plot here.

# Training Details

We use a Transformer decoder with 2 layers, 4 heads and 512 dimension size. We use a batch size of 8 and 15 epochs for training.
During training, we use two learning rate schedulers: one linearly warms-up the learning rate for the first few batches 
of the first epoch and the other decays the learning rate by a factor of 0.85 at the end of each epoch.
We use curriculum learning on the sequence length. This means that we gradually increase the length of the training samples 
to the required sequence length for the first three epochs.
We optimize the learning rate as a hyperparameter with grid-search over the choices: 5e-5, 1e-4, 2e-4, 5e-4, 1e-3.
Further, we also treat the binarization strategy described in the paper as a hyperparameter and choose the best method
by simple grid-search over the following options:
1. Threshold:
   1. Possible thresholds: 0.2, 0.4, 0.5, 0.6, 0.8
2. Threshold + merge:
   1. Possible thresholds: 0.2, 0.4, 0.5, 0.6, 0.8
   2. Possible merge distances: 2, 4, 6, 8, 10, 12, 14
3. Top-k sampling: 
   1. Possible choices for k: 2, 3, 4, 5, 6, 7, 8, 9, 10
4. Top-k sampling + merge:
   1. Possible choices for k: 3, 4, 5, 6
   2. Possible choices for merge distances: 2, 4, 6, 8 