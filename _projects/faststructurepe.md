---
layout: page
title: fast structure-informed positional encoding for music generation
description:
img:
importance: 1
---

📔 Paper: [PDF](https://github.com/agarwalmanvi/agarwalmanvi.github.io/tree/master/assets/projects/faststructurepe/fstripe.pdf)

This is the companion website to our ICASSP 2025
submission _F-StrIPE: Fast Structure-informed Positional Encoding for Music Generation_.

We display samples for the setting: train on 16 bars + test on 16 bars.
We provide samples for four methods: X-StrIPE, SPE, F-StrIPE:C and F-StrIPE:SFF:C.
Among these methods, F-StrIPE:C and X-StrIPE are methods developed by us, while SPE and F-StrIPE:SFF:C are
baselines (please refer to the paper for a full description).

For each method, we give the sample with the best score on the four metrics we reported in the paper:
1. Chroma Similarity (best = highest)
2. Grooving Similarity (best = highest)
3. Note Density Distance (best = lowest)
4. Self-Similarity Matrix Distance (best = lowest)

We render each MIDI file into audio with `muspy`.
Note that, the samples played for a given metric can be different for each method, but we preferred to do so to always play the best example for each method and to limit the number of audio examples on the demo page.
We also plot the melody tracks (in red) and the accompaniment track (in blue) as
a pianoroll and display them below with the audio. We additionally also provide the melody-only audio,
so you can compare what the added accompaniment contributes to the song.

We hope that using several metrics will give you a holistic way to assess our methods against the baselines.
In particular, we observe that chroma similarity and grooving similarity demonstrate the difference between our methods
and the baselines very effectively!

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


----------------------------------------------------------------------------------------


## Grooving Similarity

#### SPE

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

#### F-StrIPE:SFF:C

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

#### X-StrIPE

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

#### F-StrIPE:C

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


----------------------------------------------------------------------------------------


## Note Density Distance

#### SPE

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

#### F-StrIPE:SFF:C


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

#### X-StrIPE

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

#### F-StrIPE:C

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


----------------------------------------------------------------------------------------


## Self-Similarity Matrix Distance

**Quick side-note: It's not a bug, it's a feature.**
This metric measures the mean square error between the self-similarity matrix of the target and the self-similarity matrix of the prediction.
The self-similarity matrices themselves are calculated using cosine similarity.
Here, we come across a case from the testing set where the target contains no accompaniment!
This leads to a perfect SSMD score when the network predicts the accompaniment track to be empty.
This is why the pianorolls of the predictions below do not contain any accompaniment.

#### SPE

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

#### F-StrIPE:SFF:C

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

#### X-StrIPE

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

#### F-StrIPE:C

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


