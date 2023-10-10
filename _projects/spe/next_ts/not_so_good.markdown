---
layout: page
title: Next-timestep Prediction
description:
img:
importance: 1
---

## Not-So-Good examples

<br>

### Baselines

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


### Our Methods


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