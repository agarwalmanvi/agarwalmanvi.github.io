---
layout: page
title: Accompaniment Generation
description:
img:
importance: 1
---

## Not-So-Good examples

Besides the target and the prediction, we provide the melody track to give a sense of what the music 
sounds like _without_ the accompaniment track. You can find the melody track under the name of each method.

<br>

### Baselines

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

### Our Methods

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