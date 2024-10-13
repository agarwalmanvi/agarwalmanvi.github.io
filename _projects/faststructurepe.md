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
For each method, we give the example with the best score on the four metrics we reported in the paper:
Chroma Similarity (best = highest), Self-Similarity Matrix Distance (best = lowest), Grooving Similarity (best = highest) and Note Density Distance (best = lowest).
We additionally also provide the melody-only MIDI file, so you can compare what the added accompaniment contributes to the song.

⚠️ If you have problems playing the MIDI files using your browser, you can download the MIDI files here.
At this link, you can also find samples for the setting: train on 16 bars + test on 64 bars.

## Method: X-StrIPE

### Chroma Similarity

<div class="row">
    <div class="col mt-3 mt-md-0">
        <div class="row">
            Melody
        </div>
        <div class="row">
            {% include audio.liquid path="assets/projects/faststructurepe/40/melody_44.wav" controls=true %}
        </div>
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/40/melody_44.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        {% include audio.liquid path="assets/projects/faststructurepe/40/pred_44.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/projects/faststructurepe/40/pred_44.jpg" title="" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Self-Similarity Matrix Distance