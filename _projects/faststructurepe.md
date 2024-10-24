---
layout: page
title: fast structure-informed positional encoding for music generation
description:
img:
importance: 1
---

This is the companion website to our ICASSP 2025
submission _F-StrIPE: Fast Structure-informed Positional Encoding for Music Generation_.

We display samples for the setting: train on 16 bars + test on 16 bars.
We provide samples for four methods: X-StrIPE, SPE, F-StrIPE:C and F-StrIPE:SFF:C.
Among these methods, F-StrIPE:C and X-StrIPE are methods developed by us, while SPE and F-StrIPE:SFF:C are
baselines (please refer to the paper for a full description).

For each method, we give the sample with the best score on the four metrics we reported in the paper:
1. Chroma Similarity (best = highest)
2. Self-Similarity Matrix Distance (best = lowest)
3. Grooving Similarity (best = highest)
4. Note Density Distance (best = lowest)

We render each MIDI file into audio with `muspy`. We also plot the melody tracks (in red) and the accompaniment track (in blue) as
a pianoroll and display them below with the audio. We additionally also provide the melody-only audio,
so you can compare what the added accompaniment contributes to the song.

▶️ You can download the MIDI files
[here](https://github.com/agarwalmanvi/agarwalmanvi.github.io/tree/master/assets/projects/faststructurepe).

At [this link](https://github.com/agarwalmanvi/agarwalmanvi.github.io/tree/master/assets/projects/faststructurepe/train16_test64),
you can also find samples for the setting: train on 16 bars + test on 64 bars.

⚠️ This demo webpage is best viewed on a desktop! You might need to zoom in a little to see the details of the pianoroll plots.

## Chroma Similarity

#### SPE

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/60/melody_50.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/60/melody_50.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/60/pred_50.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/60/pred_50.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

#### F-StrIPE:SFF:C

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/85/melody_292.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/85/melody_292.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/85/pred_292.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/85/pred_292.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

#### X-StrIPE

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/40/melody_44.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/40/melody_44.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/40/pred_44.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/40/pred_44.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

#### F-StrIPE:C

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/102/melody_401.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/102/melody_401.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/102/pred_401.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/102/pred_401.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Method: X-StrIPE

### Self-Similarity Matrix Distance X-StrIPE

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/40/melody_159.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/40/melody_159.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/40/pred_159.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/40/pred_159.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Grooving Similarity X-StrIPE

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/40/melody_172.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/40/melody_172.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/40/pred_172.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/40/pred_172.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Note Density Distance X-StrIPE

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/40/melody_317.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/40/melody_317.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/40/pred_317.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/40/pred_317.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Method: SPE



### Self-Similarity Matrix Distance SPE

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/60/melody_215.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/60/melody_215.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/60/pred_215.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/60/pred_215.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Grooving Similarity SPE

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/60/melody_227.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/60/melody_227.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/60/pred_227.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/60/pred_227.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Note Density Distance SPE

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/60/melody_240.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/60/melody_240.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/60/pred_240.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/60/pred_240.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


## Method: F-StrIPE:C

### Self-Similarity Matrix Distance F-StrIPE:C

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/102/melody_395.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/102/melody_395.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/102/pred_395.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/102/pred_395.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Grooving Similarity F-StrIPE:C

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/102/melody_279.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/102/melody_279.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/102/pred_279.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/102/pred_279.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Note Density Distance F-StrIPE:C

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/102/melody_407.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/102/melody_407.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/102/pred_407.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/102/pred_407.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


## Method: F-StrIPE:SFF:C

### Self-Similarity Matrix Distance F-StrIPE:SFF:C

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/85/melody_399.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/85/melody_399.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/85/pred_399.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/85/pred_399.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Grooving Similarity F-StrIPE:SFF:C

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/85/melody_57.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/85/melody_57.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/85/pred_57.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/85/pred_57.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Note Density Distance F-StrIPE:SFF:C

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/faststructurepe/85/melody_5.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/85/melody_5.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody + Accompaniment
        {% include audio.liquid path="assets/projects/faststructurepe/85/pred_5.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/85/pred_5.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>