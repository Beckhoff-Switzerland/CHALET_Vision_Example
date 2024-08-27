## About This Repository
This repository is a detailed example application how to use the [CHALET_Vision](https://github.com/Beckhoff-Switzerland/CHALET_Vision) framework

The primary objective of this framework is to mitigate the considerable variance inherent to a camera system. The variance originates at the image triggering stage and persists through various lighting and camera configurations. From a basic "inaccurate" digital output to highly accurate time-synchronized outputs utilizing XFC or oversampling technology, this framework accommodates a comprehensive range of variants without significant reconfiguration of the application.

The first step is to instantiate the hardware-dependent function blocks. These generate the appropriate interface in the PLC process image. These can only be changed before compiling and downloading.
- ImageProvider - Beckhoff camera, image from file or a universal GigeVision camera
- CameraController - Software trigger, EtherCAT, EL2258, EL2595,...
- llumination - VIx2000(Beckhoff LED), EL2595
  
These are linked together when the FB_VisionSystem is created. The system forms the entire unit of a camera station.

What is the ‘Mode’ ?
As with the hardware used, there is also a high degree of variance in the control unit. Examples of this are basic functions such as: Trigger on timestamp, trigger on axis position, ...
But there are also very specific applications such as: two fast images in direct succession, where the first image is taken with white light and the second image with infrared light
The mode is an easily exchangeable function block at runtime that receives all interfaces to the hardware used from the FB_VisionSystem and thus defines the behaviour of the system

## Requirements
- [TE1000 | TwinCAT 3 Engineering](https://www.beckhoff.com/en-en/products/automation/twincat/texxxx-twincat-3-engineering/te1000.html)
- [TF7100 | TwinCAT 3 Vision Base]( https://www.beckhoff.com/de-ch/produkte/automation/twincat/tfxxxx-twincat-3-functions/tf7xxx-vision/tf7100.html)



---
## Quick Start
