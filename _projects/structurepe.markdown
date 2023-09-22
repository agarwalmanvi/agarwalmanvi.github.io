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

Below, we give some good and bad examples of both the baseline methods and our proposed methods.

## Next-timestep Prediction

<div style="display: grid;grid-template-columns: 1fr 1fr;grid-gap: 20px;border: 1px solid black;width: 100%">
    <div style="margin: 10px;border: 1px solid red">Grid Column 1
        <midi-player
          src="/assets/audio/structurepe/test.mid"
          sound-font visualizer="#myPianoRollVisualizer">
        </midi-player>
    </div>
    <div style="margin: 10px;border: 1px solid red">Grid Column 2
        <midi-player
          src="/assets/audio/structurepe/test.mid"
          sound-font visualizer="#myPianoRollVisualizer">
        </midi-player>
    </div>
</div>




Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus condimentum ex sit amet neque dignissim, vel facilisis mauris bibendum. In sed tortor dolor. Donec vel augue dignissim, dictum quam at, finibus lorem. Nulla ac lacinia ex, vitae placerat neque. Sed vitae nisl fringilla, consequat odio et, euismod odio. Donec hendrerit urna ac augue accumsan, sit amet aliquam erat sodales. Phasellus at dictum mi. Nullam finibus, mauris sed lobortis rhoncus, lacus ligula rutrum mi, id dapibus ante quam at ipsum.

Aliquam efficitur tincidunt tempor. Vestibulum faucibus est id velit accumsan blandit. Pellentesque porttitor laoreet cursus. Curabitur consectetur libero massa, in aliquam diam sodales quis. Fusce facilisis ac ex faucibus cursus. Maecenas ut leo quis leo fermentum imperdiet mattis in ante. Maecenas suscipit facilisis nisi sed semper. Vivamus porta tempus sapien nec accumsan. Aenean finibus sagittis libero eget auctor. Praesent luctus sagittis metus sed efficitur. Vivamus a tincidunt purus. Nulla tincidunt turpis leo, ac efficitur ipsum maximus a. Maecenas eget lobortis felis, eu tincidunt felis. Proin sed dolor varius, luctus libero sed, elementum dolor. Vivamus lorem nibh, finibus sed enim ac, convallis rhoncus nunc.

Ut imperdiet lacus ut magna scelerisque, eu euismod tortor porttitor. Donec vehicula viverra cursus. Pellentesque nisl neque, hendrerit nec condimentum quis, pretium non metus. Nam laoreet, orci non suscipit rhoncus, erat purus commodo urna, a laoreet nibh ipsum vitae nisi. Mauris scelerisque iaculis consequat. In elementum est vitae ex ornare porttitor. Sed turpis nulla, dignissim non dolor mollis, faucibus blandit sem. Praesent venenatis auctor tempor. Vestibulum quis placerat lectus, et vulputate ante. Praesent vitae pellentesque enim, vitae maximus nunc. Cras vitae nisl at sapien pretium dapibus ut vel justo. Ut posuere purus laoreet massa sodales, egestas molestie mi feugiat. Morbi nec libero dui. Sed eget lacus non metus blandit imperdiet a malesuada ligula. Vivamus volutpat, purus nec interdum auctor, ex elit bibendum diam, non tempor dui metus in felis.

In hac habitasse platea dictumst. Sed diam metus, bibendum ut lacus at, egestas blandit est. Phasellus at lectus mauris. Donec at vulputate massa. Phasellus quis interdum enim. Mauris mauris ligula, dictum eu dapibus in, accumsan sed erat. Sed fringilla enim quis libero ultrices, ut tincidunt urna fermentum. Maecenas sodales, nunc quis dignissim vehicula, tellus arcu aliquet est, et dapibus metus tortor at eros. Maecenas blandit ante mauris, eget rhoncus nulla cursus at. Aliquam non egestas libero. Quisque efficitur tortor leo, quis iaculis metus dictum ut. Sed a urna ac tortor dictum congue nec ac nisi.

Nunc semper tortor sit amet purus iaculis, id imperdiet erat cursus. Suspendisse vitae euismod felis. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nunc porttitor in ipsum quis rutrum. Donec posuere nulla sed justo ornare placerat. Praesent orci risus, vestibulum id viverra non, pulvinar eu eros. Vivamus sed tortor placerat, consectetur purus a, faucibus ipsum. Nam eget aliquet mi. Proin vitae iaculis enim. Nunc suscipit commodo sapien eget fringilla.

tingatingting

## Accompaniment Generation

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus condimentum ex sit amet neque dignissim, vel facilisis mauris bibendum. In sed tortor dolor. Donec vel augue dignissim, dictum quam at, finibus lorem. Nulla ac lacinia ex, vitae placerat neque. Sed vitae nisl fringilla, consequat odio et, euismod odio. Donec hendrerit urna ac augue accumsan, sit amet aliquam erat sodales. Phasellus at dictum mi. Nullam finibus, mauris sed lobortis rhoncus, lacus ligula rutrum mi, id dapibus ante quam at ipsum.

Aliquam efficitur tincidunt tempor. Vestibulum faucibus est id velit accumsan blandit. Pellentesque porttitor laoreet cursus. Curabitur consectetur libero massa, in aliquam diam sodales quis. Fusce facilisis ac ex faucibus cursus. Maecenas ut leo quis leo fermentum imperdiet mattis in ante. Maecenas suscipit facilisis nisi sed semper. Vivamus porta tempus sapien nec accumsan. Aenean finibus sagittis libero eget auctor. Praesent luctus sagittis metus sed efficitur. Vivamus a tincidunt purus. Nulla tincidunt turpis leo, ac efficitur ipsum maximus a. Maecenas eget lobortis felis, eu tincidunt felis. Proin sed dolor varius, luctus libero sed, elementum dolor. Vivamus lorem nibh, finibus sed enim ac, convallis rhoncus nunc.

Ut imperdiet lacus ut magna scelerisque, eu euismod tortor porttitor. Donec vehicula viverra cursus. Pellentesque nisl neque, hendrerit nec condimentum quis, pretium non metus. Nam laoreet, orci non suscipit rhoncus, erat purus commodo urna, a laoreet nibh ipsum vitae nisi. Mauris scelerisque iaculis consequat. In elementum est vitae ex ornare porttitor. Sed turpis nulla, dignissim non dolor mollis, faucibus blandit sem. Praesent venenatis auctor tempor. Vestibulum quis placerat lectus, et vulputate ante. Praesent vitae pellentesque enim, vitae maximus nunc. Cras vitae nisl at sapien pretium dapibus ut vel justo. Ut posuere purus laoreet massa sodales, egestas molestie mi feugiat. Morbi nec libero dui. Sed eget lacus non metus blandit imperdiet a malesuada ligula. Vivamus volutpat, purus nec interdum auctor, ex elit bibendum diam, non tempor dui metus in felis.

In hac habitasse platea dictumst. Sed diam metus, bibendum ut lacus at, egestas blandit est. Phasellus at lectus mauris. Donec at vulputate massa. Phasellus quis interdum enim. Mauris mauris ligula, dictum eu dapibus in, accumsan sed erat. Sed fringilla enim quis libero ultrices, ut tincidunt urna fermentum. Maecenas sodales, nunc quis dignissim vehicula, tellus arcu aliquet est, et dapibus metus tortor at eros. Maecenas blandit ante mauris, eget rhoncus nulla cursus at. Aliquam non egestas libero. Quisque efficitur tortor leo, quis iaculis metus dictum ut. Sed a urna ac tortor dictum congue nec ac nisi.

Nunc semper tortor sit amet purus iaculis, id imperdiet erat cursus. Suspendisse vitae euismod felis. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nunc porttitor in ipsum quis rutrum. Donec posuere nulla sed justo ornare placerat. Praesent orci risus, vestibulum id viverra non, pulvinar eu eros. Vivamus sed tortor placerat, consectetur purus a, faucibus ipsum. Nam eget aliquet mi. Proin vitae iaculis enim. Nunc suscipit commodo sapien eget fringilla.

budmtss

# Dataset Supplement

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus condimentum ex sit amet neque dignissim, vel facilisis mauris bibendum. In sed tortor dolor. Donec vel augue dignissim, dictum quam at, finibus lorem. Nulla ac lacinia ex, vitae placerat neque. Sed vitae nisl fringilla, consequat odio et, euismod odio. Donec hendrerit urna ac augue accumsan, sit amet aliquam erat sodales. Phasellus at dictum mi. Nullam finibus, mauris sed lobortis rhoncus, lacus ligula rutrum mi, id dapibus ante quam at ipsum.

Aliquam efficitur tincidunt tempor. Vestibulum faucibus est id velit accumsan blandit. Pellentesque porttitor laoreet cursus. Curabitur consectetur libero massa, in aliquam diam sodales quis. Fusce facilisis ac ex faucibus cursus. Maecenas ut leo quis leo fermentum imperdiet mattis in ante. Maecenas suscipit facilisis nisi sed semper. Vivamus porta tempus sapien nec accumsan. Aenean finibus sagittis libero eget auctor. Praesent luctus sagittis metus sed efficitur. Vivamus a tincidunt purus. Nulla tincidunt turpis leo, ac efficitur ipsum maximus a. Maecenas eget lobortis felis, eu tincidunt felis. Proin sed dolor varius, luctus libero sed, elementum dolor. Vivamus lorem nibh, finibus sed enim ac, convallis rhoncus nunc.

Ut imperdiet lacus ut magna scelerisque, eu euismod tortor porttitor. Donec vehicula viverra cursus. Pellentesque nisl neque, hendrerit nec condimentum quis, pretium non metus. Nam laoreet, orci non suscipit rhoncus, erat purus commodo urna, a laoreet nibh ipsum vitae nisi. Mauris scelerisque iaculis consequat. In elementum est vitae ex ornare porttitor. Sed turpis nulla, dignissim non dolor mollis, faucibus blandit sem. Praesent venenatis auctor tempor. Vestibulum quis placerat lectus, et vulputate ante. Praesent vitae pellentesque enim, vitae maximus nunc. Cras vitae nisl at sapien pretium dapibus ut vel justo. Ut posuere purus laoreet massa sodales, egestas molestie mi feugiat. Morbi nec libero dui. Sed eget lacus non metus blandit imperdiet a malesuada ligula. Vivamus volutpat, purus nec interdum auctor, ex elit bibendum diam, non tempor dui metus in felis.

In hac habitasse platea dictumst. Sed diam metus, bibendum ut lacus at, egestas blandit est. Phasellus at lectus mauris. Donec at vulputate massa. Phasellus quis interdum enim. Mauris mauris ligula, dictum eu dapibus in, accumsan sed erat. Sed fringilla enim quis libero ultrices, ut tincidunt urna fermentum. Maecenas sodales, nunc quis dignissim vehicula, tellus arcu aliquet est, et dapibus metus tortor at eros. Maecenas blandit ante mauris, eget rhoncus nulla cursus at. Aliquam non egestas libero. Quisque efficitur tortor leo, quis iaculis metus dictum ut. Sed a urna ac tortor dictum congue nec ac nisi.

Nunc semper tortor sit amet purus iaculis, id imperdiet erat cursus. Suspendisse vitae euismod felis. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nunc porttitor in ipsum quis rutrum. Donec posuere nulla sed justo ornare placerat. Praesent orci risus, vestibulum id viverra non, pulvinar eu eros. Vivamus sed tortor placerat, consectetur purus a, faucibus ipsum. Nam eget aliquet mi. Proin vitae iaculis enim. Nunc suscipit commodo sapien eget fringilla.

here we did some cool stuff which we will tell you about later

# Training Details

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus condimentum ex sit amet neque dignissim, vel facilisis mauris bibendum. In sed tortor dolor. Donec vel augue dignissim, dictum quam at, finibus lorem. Nulla ac lacinia ex, vitae placerat neque. Sed vitae nisl fringilla, consequat odio et, euismod odio. Donec hendrerit urna ac augue accumsan, sit amet aliquam erat sodales. Phasellus at dictum mi. Nullam finibus, mauris sed lobortis rhoncus, lacus ligula rutrum mi, id dapibus ante quam at ipsum.

Aliquam efficitur tincidunt tempor. Vestibulum faucibus est id velit accumsan blandit. Pellentesque porttitor laoreet cursus. Curabitur consectetur libero massa, in aliquam diam sodales quis. Fusce facilisis ac ex faucibus cursus. Maecenas ut leo quis leo fermentum imperdiet mattis in ante. Maecenas suscipit facilisis nisi sed semper. Vivamus porta tempus sapien nec accumsan. Aenean finibus sagittis libero eget auctor. Praesent luctus sagittis metus sed efficitur. Vivamus a tincidunt purus. Nulla tincidunt turpis leo, ac efficitur ipsum maximus a. Maecenas eget lobortis felis, eu tincidunt felis. Proin sed dolor varius, luctus libero sed, elementum dolor. Vivamus lorem nibh, finibus sed enim ac, convallis rhoncus nunc.

Ut imperdiet lacus ut magna scelerisque, eu euismod tortor porttitor. Donec vehicula viverra cursus. Pellentesque nisl neque, hendrerit nec condimentum quis, pretium non metus. Nam laoreet, orci non suscipit rhoncus, erat purus commodo urna, a laoreet nibh ipsum vitae nisi. Mauris scelerisque iaculis consequat. In elementum est vitae ex ornare porttitor. Sed turpis nulla, dignissim non dolor mollis, faucibus blandit sem. Praesent venenatis auctor tempor. Vestibulum quis placerat lectus, et vulputate ante. Praesent vitae pellentesque enim, vitae maximus nunc. Cras vitae nisl at sapien pretium dapibus ut vel justo. Ut posuere purus laoreet massa sodales, egestas molestie mi feugiat. Morbi nec libero dui. Sed eget lacus non metus blandit imperdiet a malesuada ligula. Vivamus volutpat, purus nec interdum auctor, ex elit bibendum diam, non tempor dui metus in felis.

In hac habitasse platea dictumst. Sed diam metus, bibendum ut lacus at, egestas blandit est. Phasellus at lectus mauris. Donec at vulputate massa. Phasellus quis interdum enim. Mauris mauris ligula, dictum eu dapibus in, accumsan sed erat. Sed fringilla enim quis libero ultrices, ut tincidunt urna fermentum. Maecenas sodales, nunc quis dignissim vehicula, tellus arcu aliquet est, et dapibus metus tortor at eros. Maecenas blandit ante mauris, eget rhoncus nulla cursus at. Aliquam non egestas libero. Quisque efficitur tortor leo, quis iaculis metus dictum ut. Sed a urna ac tortor dictum congue nec ac nisi.

Nunc semper tortor sit amet purus iaculis, id imperdiet erat cursus. Suspendisse vitae euismod felis. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nunc porttitor in ipsum quis rutrum. Donec posuere nulla sed justo ornare placerat. Praesent orci risus, vestibulum id viverra non, pulvinar eu eros. Vivamus sed tortor placerat, consectetur purus a, faucibus ipsum. Nam eget aliquet mi. Proin vitae iaculis enim. Nunc suscipit commodo sapien eget fringilla.