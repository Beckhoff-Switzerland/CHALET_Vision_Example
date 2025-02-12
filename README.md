## About This Repository
This repository is a detailed example application how to use the [CHALET_Vision](https://github.com/Beckhoff-Switzerland/CHALET_Vision) framework

In essence, this repository simplifies the process of integrating Beckhoff GigE Vision cameras into a Beckhoff PLC environment by providing a pre-built function block and a clear example of its usage.  The emphasis on EtherCAT timestamp triggering highlights its suitability for applications demanding precise timing.
- [VCS2000 | Area scan cameras](https://www.beckhoff.com/en-en/products/vision/cameras/vcs2000-area-scan-cameras-2.5%C2%A0gbit-s/) 
- [VUI2000 | Area scan camera unit](https://www.beckhoff.com/en-en/products/vision/units/vui2000/)
The function block provides a method to trigger images, properties for the important camera parameters and an interface to read out the captured image.

Functionality of the FB:
- **Image Triggering:** A trigger can be triggered at the desired time with a method call
- **Camera Parameter Control:** It provides access and control over important camera settings (e.g., exposure, gain, etc.).
- **Accessing image data:** The FB allows reading and accessing the captured image data.

The standard parameters are pre set so that you can start directly with the use of the high-precision EtherCAT time stamp trigger.


## Requirements
- [TE1000 | TwinCAT 3 Engineering](https://www.beckhoff.com/en-en/products/automation/twincat/texxxx-twincat-3-engineering/te1000.html)
- [TF7100 | TwinCAT 3 Vision Base]( https://www.beckhoff.com/de-ch/produkte/automation/twincat/tfxxxx-twincat-3-functions/tf7xxx-vision/tf7100.html)



## Quick Start
When the project is opened in TwinCat for the first time, certain PLC libraries are missing. These are stored in the project and can be installed using the following button.

![image](https://github.com/Beckhoff-Switzerland/CHALET_XPlanar_Example/assets/143804651/2eaaeeea-066d-446c-9530-650616aed40e)


To test the example locally, a few basic settings must be made to match the corresponding target device (IPC).
Among other things, the two network adapters available in the project must be checked and assigned to an available adapter of the device with “Compatible Devices”.
    
![image](https://github.com/user-attachments/assets/94aa0830-cec6-40ea-b93c-ea6b72038fed)


It is very likely that the camera is not recognized directly because the IP address does not match. Therefore, use the following button to search for a Gige-Vision camera in the network

![image](https://github.com/user-attachments/assets/b9bd9e2e-6ce7-4d0e-8aed-575bf53fa71d)


To trigger the first image via EtherCAT, the variable "bTriggerOnceEC" can now be set to TRUE in the PLC.

The final image can be viewed with the “ADS Image Watch” tool

![image](https://github.com/user-attachments/assets/cf551b4e-889f-44a5-ad80-71750497ced5)
