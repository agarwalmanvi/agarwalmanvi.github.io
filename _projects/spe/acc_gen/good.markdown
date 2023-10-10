---
layout: page
title: Accompaniment Generation
description:
img:
importance: 1
---

## Good examples

<br>

### Baselines

<div style="display: grid;grid-template-columns: 200px 1fr 1fr;grid-gap: 5px;width: 100%;place-items: center">
    <!-- HEADER -->
    <div style="margin: 10px">
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
    <div style="margin: 10px">
     <midi-player
     style="width: 200px"
     src="/assets/projects/structurepe/acc_gen/good/ape/6-melody_bridge.mid"
     sound-font visualizer="#myPianoRollVisualizer">
     </midi-player>
    </div>
    <div style="margin: 10px">
     <midi-player
     style="width: 200px"
     src="/assets/projects/structurepe/acc_gen/good/ape/6-tgt.mid"
     sound-font visualizer="#myPianoRollVisualizer">
     </midi-player>
    </div>
    <div style="margin: 10px">
     <midi-player
     style="width: 200px"
     src="/assets/projects/structurepe/acc_gen/good/ape/6-pred.mid"
     sound-font visualizer="#myPianoRollVisualizer">
     </midi-player>
    </div>
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
    <div style="margin: 10px">
     <midi-player
     style="width: 200px"
     src="/assets/projects/structurepe/acc_gen/good/rpe/1-melody_bridge.mid"
     sound-font visualizer="#myPianoRollVisualizer">
     </midi-player>
    </div>
    <div style="margin: 10px">
     <midi-player
     style="width: 200px"
     src="/assets/projects/structurepe/acc_gen/good/rpe/1-tgt.mid"
     sound-font visualizer="#myPianoRollVisualizer">
     </midi-player>
    </div>
    <div style="margin: 10px">
     <midi-player
     style="width: 200px"
     src="/assets/projects/structurepe/acc_gen/good/rpe/1-pred.mid"
     sound-font visualizer="#myPianoRollVisualizer">
     </midi-player>
    </div>
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
    <div style="margin: 10px">
     <midi-player
     style="width: 200px"
     src="/assets/projects/structurepe/acc_gen/good/sape_b/13-melody_bridge.mid"
     sound-font visualizer="#myPianoRollVisualizer">
     </midi-player>
    </div>
    <div style="margin: 10px">
     <midi-player
     style="width: 200px"
     src="/assets/projects/structurepe/acc_gen/good/sape_b/13-tgt.mid"
     sound-font visualizer="#myPianoRollVisualizer">
     </midi-player>
    </div>
    <div style="margin: 10px">
     <midi-player
     style="width: 200px"
     src="/assets/projects/structurepe/acc_gen/good/sape_b/13-pred.mid"
     sound-font visualizer="#myPianoRollVisualizer">
     </midi-player>
    </div>
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
    <div style="margin: 10px">
     <midi-player
     style="width: 200px"
     src="/assets/projects/structurepe/acc_gen/good/srpe_b/5-melody_bridge.mid"
     sound-font visualizer="#myPianoRollVisualizer">
     </midi-player>
    </div>
    <div style="margin: 10px">
     <midi-player
     style="width: 200px"
     src="/assets/projects/structurepe/acc_gen/good/srpe_b/5-tgt.mid"
     sound-font visualizer="#myPianoRollVisualizer">
     </midi-player>
    </div>
    <div style="margin: 10px">
     <midi-player
     style="width: 200px"
     src="/assets/projects/structurepe/acc_gen/good/srpe_b/5-pred.mid"
     sound-font visualizer="#myPianoRollVisualizer">
     </midi-player>
    </div>
    <div style="margin: 10px">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/srpe_b/5_tgt.png" style="width:175px;height:175px;">
    </div>
    <div style="margin: 10px">
    <img src="/assets/projects/structurepe/acc_gen/good/srpe_b/5_pred.png" style="width:175px;height:175px;">
    </div>
</div>