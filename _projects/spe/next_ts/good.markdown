---
layout: page
title: Next-timestep Prediction
description:
img:
importance: 1
---

<script src="https://cdn.jsdelivr.net/combine/npm/tone@14.7.58,npm/@magenta/music@1.23.1/es6/core.js,npm/focus-visible@5,npm/html-midi-player@1.5.0"></script>

## Good examples

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