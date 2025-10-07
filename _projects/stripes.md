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


### Demo

##### Sample 1

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/time/melody.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Ground truth
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/time/tgt.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Time
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/time/time_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Repetition-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/time/chord_pred.wav" controls=true %}
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

##### Sample 2

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ssmd/time/1_melody.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Ground truth
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ssmd/time/1_tgt.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Time
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ssmd/time/time_1_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Repetition-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ssmd/time/chord_1_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Key-normalized chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ssmd/time/chord_key_1_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Chroma-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ssmd/time/chord_vecs_1_pred.wav" controls=true %}
    </div>
</div>


##### Sample 3

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/chord/1_melody.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Ground truth
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/chord/1_tgt.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Time
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/chord/time_1_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Repetition-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/chord/chord_1_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Key-normalized chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/chord/chord_key_1_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Chroma-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/chord/chord_vecs_1_pred.wav" controls=true %}
    </div>
</div>


##### Sample 4

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord_vecs/1_melody.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Ground truth
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord_vecs/1_tgt.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Time
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord_vecs/time_1_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Repetition-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord_vecs/chord_1_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Key-normalized chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord_vecs/chord_key_1_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Chroma-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord_vecs/chord_vecs_1_pred.wav" controls=true %}
    </div>
</div>

##### Sample 5

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/chord_vecs/melody.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Ground truth
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/chord_vecs/tgt.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Time
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/chord_vecs/time_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Repetition-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/chord_vecs/chord_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Key-normalized chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/chord_vecs/chord_key_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Chroma-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/cs/chord_vecs/chord_vecs_pred.wav" controls=true %}
    </div>
</div>

##### Sample 6

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/gs/time/melody.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Ground truth
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/gs/time/tgt.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Time
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/gs/time/time_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Repetition-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/gs/time/chord_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Key-normalized chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/gs/time/chord_key_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Chroma-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/gs/time/chord_vecs_pred.wav" controls=true %}
    </div>
</div>

##### Sample 7

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/gs/chord/melody.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Ground truth
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/gs/chord/tgt.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Time
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/gs/chord/time_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Repetition-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/gs/chord/chord_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Key-normalized chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/gs/chord/chord_key_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Chroma-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/gs/chord/chord_vecs_pred.wav" controls=true %}
    </div>
</div>



##### Sample 8

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ssmd/time/melody.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Ground truth
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ssmd/time/tgt.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Time
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ssmd/time/time_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Repetition-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ssmd/time/chord_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Key-normalized chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ssmd/time/chord_key_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Chroma-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ssmd/time/chord_vecs_pred.wav" controls=true %}
    </div>
</div>




##### Sample 9

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord/melody.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Ground truth
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord/tgt.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Time
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord/time_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Repetition-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord/chord_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Key-normalized chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord/chord_key_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Chroma-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord/chord_vecs_pred.wav" controls=true %}
    </div>
</div>


##### Sample 10

<div class="row">
    <div class="col mt-3 mt-md-0">
        Melody
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord_key/melody.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Ground truth
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord_key/tgt.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Time
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord_key/time_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Repetition-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord_key/chord_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Key-normalized chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord_key/chord_key_pred.wav" controls=true %}
    </div>
    <div class="col mt-3 mt-md-0">
        Chroma-based chords
        {% include audio.liquid path="assets/projects/stripes/mushra_demo/ndd/chord_key/chord_vecs_pred.wav" controls=true %}
    </div>
</div>

