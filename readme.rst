🚗 Feature extraction service
-----------------------------

Extract features from a point cloud acquired by LiDAR to build a high-definition map. Classify 3D points by projecting them to a semantically segmented 2D images using the DeepLabv3+ model

- https://ruslo.github.io/segmentation_classes_docs/

.. image:: https://img.youtube.com/vi/QsgAw3NTl3s/maxresdefault.jpg
    :alt: Features extraction demo
    :target: https://www.youtube.com/watch?v=QsgAw3NTl3s

- Images labeled using the https://www.v7labs.com/darwin platform
- DeepLabV3+ model trained on TPU in Google Cloud
- [DeepLab] Related fixes:

  - https://github.com/tensorflow/models/pull/8866 (Fix generation of tfrecord for Cityscapes)
  - https://github.com/tensorflow/models/pull/8870 (Cityscapes splits refactoring)

- [PCL] Fix illegal memory access in CUDA octree builder:

  - https://github.com/PointCloudLibrary/pcl/issues/2371
  - https://github.com/PointCloudLibrary/pcl/pull/3627
- [CloudCompare] Reported bugs:

  - https://github.com/CloudCompare/CloudCompare/issues/1586
  - https://github.com/CloudCompare/CloudCompare/issues/1612
  - https://github.com/CloudCompare/CloudCompare/issues/1615

🚁 I-Seed
---------

Flight onboard service for Manifold 2-G of DJI Matrice 300 RTK. Object detection by YOLOv5 model of the artificial seeds spread over an area using Nvidia TensorRT on Jetson TX2 GPU

- https://github.com/Olyseus/i_seed_drone_onboard (C++/DJI Payload SDK, `SDK Interconnection <https://developer.dji.com/document/21e06b1f-393b-48ba-a97c-66caa482ac9d>`__)
- https://olyseus.github.io/i_seed_drone_onboard (Doxygen)
- https://github.com/Olyseus/i_seed_drone_control (Java/DJI Mobile SDK, MVP)
- https://iseedproject.eu/

🔧 CMake
--------

- Add `file(LOCK) <https://cmake.org/cmake/help/v3.14/command/file.html#locking>`__ command: https://gitlab.kitware.com/cmake/cmake/-/commit/e6db4c5
- LTO/IPO support for GCC/Clang, Android/Linux/iOS/macOS: `#16665 <https://gitlab.kitware.com/cmake/cmake/issues/16665#note_236443>`__ (Available since `CMake 3.9 <https://cmake.org/cmake/help/v3.9/release/3.9.html#other>`__)
- Install universal device+simulator iOS libraries: `565d080 <https://gitlab.kitware.com/cmake/cmake/commit/565d080a9a1e133bda868e905226181b60e90356>`__ (`iOS cross-compiling <https://cmake.org/cmake/help/v3.14/manual/cmake-toolchains.7.html#cross-compiling-for-ios-tvos-or-watchos>`__)
- *...and other various fixes*: https://gitlab.kitware.com/cmake/cmake/-/commits/master?author=Ruslan%20Baratov

😌 C++
------

- Report C++ standard defect:

  - https://cplusplus.github.io/LWG/issue3756
- [clang] Killed Clang 3.3 with one line of code:

  - https://bugs.llvm.org/show_bug.cgi?id=17255
  - ``echo 'operator()(){return typename A::template B<>;}' | clang++ -x c++ -``
- [clang] Report violation of C++ 2003 standard, 5.3.3, [expr.sizeof]

  - https://bugs.llvm.org/show_bug.cgi?id=16872
- [libc++] Fix typo in ``std::midpoint``:

  - https://reviews.llvm.org/D71525

- [libc++] Report ``std::string::resize`` bugs:

  - https://bugs.llvm.org/show_bug.cgi?id=17771 (Unexpected ``length_error``)
  - https://bugs.llvm.org/show_bug.cgi?id=17148 (Segmentation fault with ``max_size - 1``)
- [Qt] ``QCameraViewfinderSettingsControl2`` for Android:

  - https://codereview.qt-project.org/c/qt/qtmultimedia/+/150849
  - https://github.com/qt/qtmultimedia/commit/62d9b69
- [fmt] Benchmarks leading to performance improvements:

  - https://github.com/ruslo/int-dec-format-tests
  - https://github.com/fmtlib/fmt/commit/2f423d8
  - https://github.com/fmtlib/fmt/commit/e9b2191
  - https://github.com/fmtlib/fmt/commit/3017fc6

📄 OpenSSL
----------

Documentation fixes:

- https://github.com/openssl/openssl/pull/24520 (SSL_*_use will increment reference counter)
- https://github.com/openssl/openssl/pull/24478 (Notes about freeing objects)
- https://github.com/openssl/openssl/pull/24435 (Default value for verification flags is 'SSL_VERIFY_NONE')
- https://github.com/openssl/openssl/pull/24375 ('SSL_CTX_set_cert_store' ownership of 'store')

💀 Old
------

- https://github.com/ruslo/hunter |hunter_stars|

  - CMake driven cross-platform package manager for C/C++ 
  - Moved to https://github.com/cpp-pm/hunter
- https://github.com/ruslo/polly |polly_stars|

  - Collection of CMake toolchains
- https://github.com/ruslo/CGold |cgold_stars|

  - The Hitchhiker’s Guide to the CMake
- https://github.com/elucideye/drishti |drishti_stars|

  - Real time eye tracking (*only CMake maintenance*)

.. |hunter_stars| image:: https://img.shields.io/github/stars/ruslo/hunter
  :target: https://github.com/ruslo/hunter
  :alt: Hunter stars

.. |polly_stars| image:: https://img.shields.io/github/stars/ruslo/polly
  :target: https://github.com/ruslo/polly
  :alt: Polly stars

.. |cgold_stars| image:: https://img.shields.io/github/stars/ruslo/cgold
  :target: https://github.com/ruslo/cgold
  :alt: CGold stars

.. |drishti_stars| image:: https://img.shields.io/github/stars/elucideye/drishti
  :target: https://github.com/elucideye/drishti
  :alt: Drishti stars
