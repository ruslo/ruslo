Feature extraction service
--------------------------

Extract features from a point cloud acquired by LiDAR to build a high-definition map. Classify 3D points by projecting them to a semantically segmented 2D images using the DeepLabv3+ model

- https://ruslo.github.io/segmentation_classes_docs/

.. image:: https://img.youtube.com/vi/QsgAw3NTl3s/maxresdefault.jpg
    :alt: Features extraction demo
    :target: https://www.youtube.com/watch?v=QsgAw3NTl3s

- Images labeled using the https://www.v7labs.com/darwin platform
- DeepLabV3+ model trained on TPU in Google Cloud
- Related fixes:

  - https://github.com/tensorflow/models/pull/8866 (Fix generation of tfrecord for Cityscapes)
  - https://github.com/tensorflow/models/pull/8870 (Cityscapes splits refactoring)

I-Seed
------

Flight onboard service for Manifold 2-G of DJI Matrice 300 RTK. Object detection by YOLOv5 model of the artificial seeds spread over an area using Nvidia TensorRT on Jetson TX2 GPU

- https://github.com/Olyseus/i_seed_drone_onboard (C++/DJI Payload SDK, `SDK Interconnection <https://developer.dji.com/document/21e06b1f-393b-48ba-a97c-66caa482ac9d>`__)
- https://olyseus.github.io/i_seed_drone_onboard (Doxygen)
- https://github.com/Olyseus/i_seed_drone_control (Java/DJI Mobile SDK, MVP)
- https://iseedproject.eu/
