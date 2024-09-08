---
layout: page
title: structure-informed positional encoding for music generation
description:
img:
importance: 2
---

<script src="https://cdn.jsdelivr.net/combine/npm/tone@14.7.58,npm/@magenta/music@1.23.1/es6/core.js,npm/focus-visible@5,npm/html-midi-player@1.5.0"></script>

This is the companion website to our ICASSP 2024 paper: _Structure-informed Positional Encoding for Music Generation_.<br><br>

📢 NEW! Our paper was selected for an oral presentation! If you are at ICASSP 2024, you can find us presenting this work at session **AASP-L2** in Room 105 at 17:50 on Tuesday, April 16, 2024. See you in Seoul!

---

💻 Code: [GitHub](https://github.com/agarwalmanvi/structurePE)<br>
💾 Dataset: [Zenodo](https://zenodo.org/records/10932363)<br>
📔 Paper: [arXiV](https://arxiv.org/abs/2402.13301v2)
[HAL](https://hal.science/hal-04432659v3)
[IEEE](https://doi.org/10.1109/ICASSP48485.2024.10448149)<br>
🔗 DOI: 10.1109/ICASSP48485.2024.10448149

---

# Contents

1. [Training Details](#training-details)
2. [Dataset Supplement](#dataset-supplement)
3. [Generated Samples](#generated-samples)
   1. [Next-timestep Prediction](#next-timestep-prediction): jump to good examples (<a href="#nexttsgoodbaselines">Baselines</a>, <a href="#nexttsgoodours">Our Methods</a>) and bad examples (<a href="#nexttsbadbaselines">Baselines</a>, <a href="#nexttsbadours">Our Methods</a>)
   2. [Accompaniment Generation](#accompaniment-generation): jump to good examples (<a href="#accgoodbaselines">Baselines</a>, <a href="#accgoodours">Our Methods</a>) and bad examples (<a href="#accbadbaselines">Baselines</a>, <a href="#accbadours">Our Methods</a>)

<br><br>

# Training Details

We use a Transformer decoder with 2 layers, 4 heads and 512 dimension size. We use a batch size of 8 and 15 epochs for training.
During training, we use two learning rate schedulers: one linearly warms-up the learning rate for the first few batches of the first epoch and the other decays the learning rate by a factor of 0.85 at the end of each epoch.
We use curriculum learning on the sequence length. This means that we gradually increase the length of the training samples to the required sequence length for the first three epochs.
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

<br><br>

# Dataset Supplement

The dataset we use is the Chinese POP909 dataset, which comes with structural annotations.
The MIDI songs are cleanly divided into three tracks: melody, bridge and piano. We first convert them into pianorolls.
We select only those songs with a 4/4 time signature and that are long enough to provide at least one sample, giving us a total of 866 songs.

The structural labels contain four categories for each timestep, with each category corresponding to a different temporal resolution: tempo, section, chord and melody.
However, these annotations are not properly aligned with the MIDI file due to two sources of variable-length error:

1. silence at the beginning of the song
2. musical phrases that are not included in the labeling, such as pickup measures

Although the first source of error is trivial to eliminate, the second cannot be corrected with high precision in an automated fashion.
Hence, I manually select the beat position at which the structural annotations should start for each song.
Below, I show the validation loss for a selection of baselines and proposed methods, using 20% of the dataset.

<div style="display:grid; grid-template-columns:1fr 1fr; grid-gap:5px; width:100%; place-items: center">
  <!-- HEADER -->
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/figs/next_ts.png" alt="Next-timestep Prediction" style="width: 375px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/figs/acc_gen.png" alt="Accompaniment Generation" style="width: 375px">
  </div>
</div>

<br><br>

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

Along with the samples, we also plot the self-similarity matrices depicting the structure of the corresponding song.

## Next-timestep Prediction

### Good Examples

<h4 id="nexttsgoodbaselines">Baselines</h4>

<div style="display:grid; grid-template-columns:100px 1fr 1fr; grid-gap:5px; width:100%; place-items: center">
  <!-- HEADER -->
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px;width: 225px;height: 30px;text-align: center">
  Target
  </div>
  <div style="margin: 10px;width: 225px;height: 30px;text-align: center">
  Prediction
  </div>
  <!-- NoPE -->
  <div style="margin: 10px">
     <code>NoPE</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/good/nope/1-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/good/nope/1-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/nope/1_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/nope/1_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- APE -->
  <div style="margin: 10px">
     <code>APE</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/good/ape/1-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/good/ape/1-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/ape/1_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/ape/1_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- RPE -->
  <div style="margin: 10px">
     <code>RPE</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/good/rpe/0-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/good/rpe/0-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/rpe/0_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/rpe/0_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- S-APE/b -->
  <div style="margin: 10px">
     <code>S-APE/b</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/good/sape_b/12-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/good/sape_b/12-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/sape_b/12_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/sape_b/12_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- S-RPE/b -->
  <div style="margin: 10px">
     <code>S-RPE/b</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/good/srpe_b/10-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/good/srpe_b/10-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/srpe_b/10_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/srpe_b/10_pred.png" style="width:175px;height:175px;">
  </div>
</div>

<h4 id="nexttsgoodours">Our Methods</h4>

<div style="display: grid;grid-template-columns: 100px 1fr 1fr;grid-gap: 5px;width: 100%;place-items: center">
  <!-- HEADER -->
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px;width: 225px;height: 30px;text-align: center">
  Target
  </div>
  <div style="margin: 10px;width: 225px;height: 30px;text-align: center">
  Prediction
  </div>
  <!-- L S-APE -->
  <div style="margin: 10px">
     <code>L S-APE</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/good/sape/4-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/good/sape/4-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/sape/4_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/sape/4_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- S S-APE -->
  <div style="margin: 10px">
     <code>S S-APE</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/good/ssape/20-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/good/ssape/20-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/ssape/20_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/ssape/20_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- L S-RPE -->
  <div style="margin: 10px">
     <code>L S-RPE</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/good/srpe/11-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/good/srpe/11-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/srpe/11_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/srpe/11_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- S S-RPE -->
  <div style="margin: 10px">
     <code>S S-RPE/b</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/good/ssrpe/24-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/good/ssrpe/24-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/ssrpe/24_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/ssrpe/24_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- NS-RPE/c -->
  <div style="margin: 10px">
     <code>NS-RPE/c</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/good/nsrpe_c/10-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/good/nsrpe_c/10-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/nsrpe_c/10_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/nsrpe_c/10_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- NS-RPE/s -->
  <div style="margin: 10px">
     <code>NS-RPE/s</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/good/nsrpe_s/5-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/good/nsrpe_s/5-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/nsrpe_s/5_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/good/nsrpe_s/5_pred.png" style="width:175px;height:175px;">
  </div>
</div>

### Bad Examples

<h4 id="nexttsbadbaselines">Baselines</h4>

<div style="display:grid; grid-template-columns:100px 1fr 1fr; grid-gap:5px; width:100%; place-items: center">
  <!-- HEADER -->
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px;width: 225px;height: 30px;text-align: center">
  Target
  </div>
  <div style="margin: 10px;width: 225px;height: 30px;text-align: center">
  Prediction
  </div>
  <!-- NoPE -->
  <div style="margin: 10px">
     <code>NoPE</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/nope/0-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/nope/0-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/nope/0_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/nope/0_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- APE -->
  <div style="margin: 10px">
     <code>APE</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/ape/0-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/ape/0-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/ape/0_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/ape/0_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- RPE -->
  <div style="margin: 10px">
     <code>RPE</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/rpe/0-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/rpe/0-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/rpe/0_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/rpe/0_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- S-APE/b -->
  <div style="margin: 10px">
     <code>S-APE/b</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/sape_b/1-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/sape_b/1-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/sape_b/1_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/sape_b/1_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- S-RPE/b -->
  <div style="margin: 10px">
     <code>S-RPE/b</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/srpe_b/1-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/srpe_b/1-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/srpe_b/1_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/srpe_b/1_pred.png" style="width:175px;height:175px;">
  </div>
</div>

<h4 id="nexttsbadours">Our Methods</h4>

<div style="display: grid;grid-template-columns: 100px 1fr 1fr;grid-gap: 5px;width: 100%;place-items: center">
  <!-- HEADER -->
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px;width: 225px;height: 30px;text-align: center">
  Target
  </div>
  <div style="margin: 10px;width: 225px;height: 30px;text-align: center">
  Prediction
  </div>
  <!-- L S-APE -->
  <div style="margin: 10px">
     <code>L S-APE</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/sape/0-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/sape/0-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/sape/0_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/sape/0_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- S S-APE -->
  <div style="margin: 10px">
     <code>S S-APE</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/ssape/1-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/ssape/1-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/ssape/1_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/ssape/1_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- L S-RPE -->
  <div style="margin: 10px">
     <code>L S-RPE</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/srpe/0-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/srpe/0-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/srpe/0_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/srpe/0_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- S S-RPE -->
  <div style="margin: 10px">
     <code>S S-RPE/b</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/ssrpe/4-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/ssrpe/4-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/ssrpe/4_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/ssrpe/4_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- NS-RPE/c -->
  <div style="margin: 10px">
     <code>NS-RPE/c</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/nsrpe_c/6-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/nsrpe_c/6-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/nsrpe_c/6_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/nsrpe_c/6_pred.png" style="width:175px;height:175px;">
  </div>
  <!-- NS-RPE/s -->
  <div style="margin: 10px">
     <code>NS-RPE/s</code>
  </div>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/nsrpe_s/10-tgt.wav" style="width:225px; margin:10px">
  </audio>
  <audio controls src="/assets/projects/structurepe/next_ts/less_good/nsrpe_s/10-pred.wav" style="width:225px; margin:10px">
  </audio>
  <div style="margin: 10px">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/nsrpe_s/10_tgt.png" style="width:175px;height:175px;">
  </div>
  <div style="margin: 10px">
  <img src="/assets/projects/structurepe/next_ts/less_good/nsrpe_s/10_pred.png" style="width:175px;height:175px;">
  </div>
</div>

## Accompaniment Generation

Besides the target and the prediction, we provide the melody track to give a sense of what the music sounds like _without_ the accompaniment track. You can find the melody track under the name of each method.

### Good Examples

<h4 id="accgoodbaselines">Baselines</h4>

<div style="display: grid;grid-template-columns: 200px 1fr 1fr;grid-gap: 5px;width: 100%;place-items: center">
    <!-- HEADER -->
    <div style="margin: 10px;width: 200px;text-align: center">
    Melody
    </div>
    <div style="margin: 10px;width: 200px;text-align: center">
    Target
    </div>
    <div style="margin: 10px;width: 200px;text-align: center">
    Prediction
    </div>
    <!-- NoPE -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>NoPE</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/nope/1-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/nope/1-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/nope/1-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/nope/1_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/nope/1_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- APE -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>APE</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/ape/6-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/ape/6-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/ape/6-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/ape/6_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/ape/6_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- RPE -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>RPE</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/rpe/1-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/rpe/1-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/rpe/1-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/rpe/1_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/rpe/1_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- S-APE/b -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>S-APE/b</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/sape_b/13-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/sape_b/13-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/sape_b/13-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/sape_b/13_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/sape_b/13_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- S-RPE/b -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>S-RPE/b</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/srpe_b/5-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/srpe_b/5-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/srpe_b/5-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/srpe_b/5_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/srpe_b/5_pred.png" style="width:175px;height:175px;">
    </div>
</div>

<h4 id="accgoodours">Our Methods</h4>

<div style="display: grid;grid-template-columns: 200px 1fr 1fr;grid-gap: 5px;width: 100%;place-items: center">
    <!-- HEADER -->
    <div style="margin: 10px;width: 200px;text-align: center">
    Melody
    </div>
    <div style="margin: 10px;width: 200px;text-align: center">
    Target
    </div>
    <div style="margin: 10px;width: 200px;text-align: center">
    Prediction
    </div>
    <!-- L S-APE -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>L S-APE</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/sape/3-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/sape/3-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/sape/3-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/sape/3_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/sape/3_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- S S-APE -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>S S-APE</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/ssape/7-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/ssape/7-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/ssape/7-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/ssape/7_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/ssape/7_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- L S-RPE -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>L S-RPE</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/srpe/6-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/srpe/6-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/srpe/6-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/srpe/6_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/srpe/6_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- S S-RPE -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>S S-RPE</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/ssrpe/3-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/ssrpe/3-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/ssrpe/3-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/ssrpe/3_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/ssrpe/3_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- NS-RPE/c -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>NS-RPE/c</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/nsrpe_c/35-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/nsrpe_c/35-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/nsrpe_c/35-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/nsrpe_c/35_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/nsrpe_c/35_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- NS-RPE/s -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>NS-RPE/s</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/nsrpe_s/20-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/nsrpe_s/20-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/good/nsrpe_s/20-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/nsrpe_s/20_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/nsrpe_s/20_pred.png" style="width:175px;height:175px;">
    </div>
</div>

### Bad Examples

<h4 id="accbadbaselines">Baselines</h4>

<div style="display: grid;grid-template-columns: 200px 1fr 1fr;grid-gap: 5px;width: 100%;place-items: center">
    <!-- HEADER -->
    <div style="margin: 10px;width: 200px;text-align: center">
    Melody
    </div>
    <div style="margin: 10px;width: 200px;text-align: center">
    Target
    </div>
    <div style="margin: 10px;width: 200px;text-align: center">
    Prediction
    </div>
    <!-- NoPE -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>NoPE</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/nope/34-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/nope/34-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/nope/34-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/nope/34_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/nope/34_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- APE -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>APE</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/ape/1-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/ape/1-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/ape/1-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/ape/1_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/ape/1_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- RPE -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>RPE</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/rpe/1-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/rpe/1-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/rpe/1-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/rpe/1_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/rpe/1_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- S-APE/b -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>S-APE/b</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/sape_b/4-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/sape_b/4-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/sape_b/4-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/sape_b/4_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/sape_b/4_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- S-RPE/b -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>S-RPE/b</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/srpe_b/2-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/srpe_b/2-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/srpe_b/2-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/srpe_b/2_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/srpe_b/2_pred.png" style="width:175px;height:175px;">
    </div>
</div>

<h4 id="accbadours">Our Methods</h4>

<div style="display: grid;grid-template-columns: 200px 1fr 1fr;grid-gap: 5px;width: 100%;place-items: center">
    <!-- HEADER -->
    <div style="margin: 10px;width: 200px;text-align: center">
    Melody
    </div>
    <div style="margin: 10px;width: 200px;text-align: center">
    Target
    </div>
    <div style="margin: 10px;width: 200px;text-align: center">
    Prediction
    </div>
    <!-- L S-APE -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>L S-APE</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/sape/5-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/sape/5-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/sape/5-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/sape/5_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/sape/5_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- S S-APE -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>S S-APE</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/ssape/0-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/ssape/0-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/ssape/0-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/ssape/0_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/ssape/0_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- L S-RPE -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>L S-RPE</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/srpe/0-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/srpe/0-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/srpe/0-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/srpe/0_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/srpe/0_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- S S-RPE -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>S S-RPE</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/ssrpe/3-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/ssrpe/3-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/ssrpe/3-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/ssrpe/3_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/ssrpe/3_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- NS-RPE/c -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>NS-RPE/c</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/nsrpe_c/0-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/nsrpe_c/0-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/nsrpe_c/0-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/nsrpe_c/0_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/nsrpe_c/0_pred.png" style="width:175px;height:175px;">
    </div>
    <!-- NS-RPE/s -->
    <div style="margin: 10px;text-align: center;height: 20px">
     <code>NS-RPE/s</code>
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <div style="margin: 10px;text-align: center;height: 20px">
    </div>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/nsrpe_s/27-melody_bridge.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/nsrpe_s/27-tgt.wav" style="width:200px; margin:10px">
    </audio>
    <audio controls src="/assets/projects/structurepe/acc_gen/less_good/nsrpe_s/27-pred.wav" style="width:200px; margin:10px">
    </audio>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/nsrpe_s/27_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/less_good/nsrpe_s/27_pred.png" style="width:175px;height:175px;">
    </div>
</div>

<br><br>

# Demo for ICASSP oral presentation

<br>

<div style="display:grid; grid-template-columns:1fr 1fr; grid-gap:5px; width:100%; place-items: center">
<div>Melody + Bridge</div><div>Melody + Bridge + Accompaniment</div>
<div>
<audio controls src="/assets/projects/structurepe/demo/12-melody_bridge.wav" style="width:225px; margin:10px">
</audio>
</div>
<div>
<audio controls src="/assets/projects/structurepe/demo/12-pred.wav" style="width:225px; margin:10px">
</audio>
</div>
</div>

<br><br><br><br><br>
