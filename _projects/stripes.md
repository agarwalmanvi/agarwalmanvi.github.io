---
layout: page
title: Of All StrIPEs 🐯
description:
img:
importance: 1
---

## Investigating Structure-informed Positional Encoding for Efficient Music Generation

📔 Paper: [arXiV](https://arxiv.org/abs/2504.05364)
[HAL](https://hal.science/hal-05021809/)


#### Demo

###### Sample 1

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/time/melody.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Time
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/time/time_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Repetition-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/time/chord_pred.wav" controls=true %}
    </div>
</div>

<div class="row">
    <div class="col mt-3 mt-md-0">
        Ground truth
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/time/tgt.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Key-normalized chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/time/chord_key_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Chroma-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/time/chord_vecs_pred.wav" controls=true %}
    </div>
</div>
