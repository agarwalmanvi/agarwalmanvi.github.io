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

### Good examples

<details style="margin-top: 15px; margin-bottom: 15px; margin-left: 5px">
   <summary><b>Baselines</b></summary>
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
      <!-- NoPE -->
      <div style="margin: 10px">
         <code>NoPE</code>
      </div>
      <div style="margin: 10px">
         <midi-player
         style="width: 225px"
         src="/assets/projects/structurepe/next_ts/good/nope/1-tgt.mid"
         sound-font visualizer="#myPianoRollVisualizer">
         </midi-player>
      </div>
      <div style="margin: 10px">
         <midi-player
         style="width: 225px"
         src="/assets/projects/structurepe/next_ts/good/nope/1-pred.mid"
         sound-font visualizer="#myPianoRollVisualizer">
         </midi-player>
      </div>
      <div style="margin: 10px">
      </div>
      <div style="margin: 10px">
      <img src="/assets/projects/structurepe/next_ts/good/nope/1_tgt.png" style="width:128px;height:128px;">
      </div>
      <div style="margin: 10px">
      <img src="/assets/projects/structurepe/next_ts/good/nope/1_pred.png" style="width:128px;height:128px;">
      </div>
      <!-- APE -->
      <div style="margin: 10px">
         <code>APE</code>
      </div>
      <div style="margin: 10px">
         <midi-player
         style="width: 225px"
         src="/assets/audio/structurepe/test.mid"
         sound-font visualizer="#myPianoRollVisualizer">
         </midi-player>
      </div>
      <div style="margin: 10px">
         <midi-player
         style="width: 225px"
         src="/assets/audio/structurepe/test.mid"
         sound-font visualizer="#myPianoRollVisualizer">
         </midi-player>
      </div>
      <div style="margin: 10px">
      </div>
      <div style="margin: 10px;width: 225px;height: 100px;border: 1px dashed black">
      </div>
      <div style="margin: 10px;width: 225px;height: 100px;border: 1px dashed black">
      </div>
   </div>
</details>

### Not-so-good examples
<!--
<details style="margin-left: 20px; margin-top: 20px; margin-bottom: 10px">
<summary><b><font size="+1">Good Examples</font></b></summary>
   <details style="margin-left: 10px; margin-top: 5px">
   <summary>Baselines</summary>
   <div style="display: grid;grid-template-columns: 100px 1fr 1fr;grid-gap: 5px;width: 100%;place-items: center">
      <div style="margin: 10px">
         <code>NoPE</code>
      </div>
      <div style="margin: 10px">
         <midi-player
         style="width: 225px"
         src="/assets/audio/structurepe/test.mid"
         sound-font visualizer="#myPianoRollVisualizer">
         </midi-player>
      </div>
      <div style="margin: 10px">
         <midi-player
         style="width: 225px"
         src="/assets/audio/structurepe/test.mid"
         sound-font visualizer="#myPianoRollVisualizer">
         </midi-player>
      </div>
      <div style="margin: 10px">
         <code>APE</code>
      </div>
      <div style="margin: 10px">
         <midi-player
         style="width: 225px"
         src="/assets/audio/structurepe/test.mid"
         sound-font visualizer="#myPianoRollVisualizer">
         </midi-player>
      </div>
      <div style="margin: 10px">
         <midi-player
         style="width: 225px"
         src="/assets/audio/structurepe/test.mid"
         sound-font visualizer="#myPianoRollVisualizer">
         </midi-player>
      </div>
   </div>
   </details>
   <details style="margin-left: 10px; margin-top: 5px">
   <summary>Our Methods</summary>
   <div style="display: grid;grid-template-columns: 100px 1fr 1fr;grid-gap: 5px;width: 100%;place-items: center">
      <div style="margin: 10px">
      </div>
      <div style="margin: 10px;width: 225px;height: 30px;text-align: center">
      Target
      </div>
      <div style="margin: 10px;width: 225px;height: 30px;text-align: center">
      Prediction
      </div>
      <div style="margin: 10px">
         <code>L-SAPE</code>
      </div>
      <div style="margin: 10px">
         <midi-player
         style="width: 225px"
         src="/assets/audio/structurepe/test.mid"
         sound-font visualizer="#myPianoRollVisualizer">
         </midi-player>
      </div>
      <div style="margin: 10px">
         <midi-player
         style="width: 225px"
         src="/assets/audio/structurepe/test.mid"
         sound-font visualizer="#myPianoRollVisualizer">
         </midi-player>
      </div>
      <div style="margin: 10px">
      </div>
      <div style="margin: 10px;width: 225px;height: 100px;border: 1px dashed black">
      </div>
      <div style="margin: 10px;width: 225px;height: 100px;border: 1px dashed black">
      </div>
      <div style="margin: 10px">
         <code>S-SAPE</code>
      </div>
      <div style="margin: 10px">
         <midi-player
         style="width: 225px"
         src="/assets/audio/structurepe/test.mid"
         sound-font visualizer="#myPianoRollVisualizer">
         </midi-player>
      </div>
      <div style="margin: 10px">
         <midi-player
         style="width: 225px"
         src="/assets/audio/structurepe/test.mid"
         sound-font visualizer="#myPianoRollVisualizer">
         </midi-player>
      </div>
      <div style="margin: 10px">
      </div>
      <div style="margin: 10px;width: 225px;height: 100px;border: 1px dashed black">
      </div>
      <div style="margin: 10px;width: 225px;height: 100px;border: 1px dashed black">
      </div>
   </div>
   </details>
</details>
-->
## Accompaniment Generation

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus condimentum ex sit amet neque dignissim, vel facilisis mauris bibendum. In sed tortor dolor. Donec vel augue dignissim, dictum quam at, finibus lorem. Nulla ac lacinia ex, vitae placerat neque. Sed vitae nisl fringilla, consequat odio et, euismod odio. Donec hendrerit urna ac augue accumsan, sit amet aliquam erat sodales. Phasellus at dictum mi. Nullam finibus, mauris sed lobortis rhoncus, lacus ligula rutrum mi, id dapibus ante quam at ipsum.

Aliquam efficitur tincidunt tempor. Vestibulum faucibus est id velit accumsan blandit. Pellentesque porttitor laoreet cursus. Curabitur consectetur libero massa, in aliquam diam sodales quis. Fusce facilisis ac ex faucibus cursus. Maecenas ut leo quis leo fermentum imperdiet mattis in ante. Maecenas suscipit facilisis nisi sed semper. Vivamus porta tempus sapien nec accumsan. Aenean finibus sagittis libero eget auctor. Praesent luctus sagittis metus sed efficitur. Vivamus a tincidunt purus. Nulla tincidunt turpis leo, ac efficitur ipsum maximus a. Maecenas eget lobortis felis, eu tincidunt felis. Proin sed dolor varius, luctus libero sed, elementum dolor. Vivamus lorem nibh, finibus sed enim ac, convallis rhoncus nunc.

Ut imperdiet lacus ut magna scelerisque, eu euismod tortor porttitor. Donec vehicula viverra cursus. Pellentesque nisl neque, hendrerit nec condimentum quis, pretium non metus. Nam laoreet, orci non suscipit rhoncus, erat purus commodo urna, a laoreet nibh ipsum vitae nisi. Mauris scelerisque iaculis consequat. In elementum est vitae ex ornare porttitor. Sed turpis nulla, dignissim non dolor mollis, faucibus blandit sem. Praesent venenatis auctor tempor. Vestibulum quis placerat lectus, et vulputate ante. Praesent vitae pellentesque enim, vitae maximus nunc. Cras vitae nisl at sapien pretium dapibus ut vel justo. Ut posuere purus laoreet massa sodales, egestas molestie mi feugiat. Morbi nec libero dui. Sed eget lacus non metus blandit imperdiet a malesuada ligula. Vivamus volutpat, purus nec interdum auctor, ex elit bibendum diam, non tempor dui metus in felis.

In hac habitasse platea dictumst. Sed diam metus, bibendum ut lacus at, egestas blandit est. Phasellus at lectus mauris. Donec at vulputate massa. Phasellus quis interdum enim. Mauris mauris ligula, dictum eu dapibus in, accumsan sed erat. Sed fringilla enim quis libero ultrices, ut tincidunt urna fermentum. Maecenas sodales, nunc quis dignissim vehicula, tellus arcu aliquet est, et dapibus metus tortor at eros. Maecenas blandit ante mauris, eget rhoncus nulla cursus at. Aliquam non egestas libero. Quisque efficitur tortor leo, quis iaculis metus dictum ut. Sed a urna ac tortor dictum congue nec ac nisi.

Nunc semper tortor sit amet purus iaculis, id imperdiet erat cursus. Suspendisse vitae euismod felis. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nunc porttitor in ipsum quis rutrum. Donec posuere nulla sed justo ornare placerat. Praesent orci risus, vestibulum id viverra non, pulvinar eu eros. Vivamus sed tortor placerat, consectetur purus a, faucibus ipsum. Nam eget aliquet mi. Proin vitae iaculis enim. Nunc suscipit commodo sapien eget fringilla.

budmtss

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