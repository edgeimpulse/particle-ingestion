# Edge Impulse's Particle Ingestion Project

For more information see our [Particle Photon 2](https://docs.edgeimpulse.com/docs/edge-ai-hardware/mcu/particle-photon-2) or [Particle Boron](https://docs.edgeimpulse.com/docs/edge-ai-hardware/mcu/particle-boron)
documentation.

## Hardware
The ingestion firmware is based on the Particle Photon2 and Boron devices. The Photon2 uses the [Analog Devices ADXL362](https://www.analog.com/media/en/technical-documentation/data-sheets/adxl362.pdf) while the Boron uses the [Analog Devices ADXL345](https://www.analog.com/media/en/technical-documentation/data-sheets/adxl345.pdf)

The library used and included in this project for the Photon 2 can be found [here](https://github.com/rickkas7/ADXL362DMA) This repository also explains how to connect the ADXL362 to the Photon2. For the Boron the library is included in the project properties file dependency list.

## Setup

### Particle Tools
Make sure you've installed the particle tools. You can either use [particle cli](https://docs.particle.io/getting-started/developer-tools/cli/) or the VSCode extension [Workbench IDE](https://docs.particle.io/getting-started/developer-tools/workbench/) (recommended).

### Edge Impulse CLI
For uploading data to studio, the `edge-impulse-data-forwarder` tool is used. This is included in the Edge Impulse CLI tools which can be downloaded [here](https://www.npmjs.com/package/edge-impulse-cli)


## Build and Flash (locally): in Particle Workbench

1. In Workbench, select **Particle: Import Project** and select the `project.properties` file in the directory that you just downloaded and extracted.

1. Use **Particle: Configure Project for Device** and select **deviceOS@5.8.0 (or a later version)** and choose a target. (e.g. **Photon 2/P2** or **Boron**).

1. Compile with  **Particle: Compile application (local)**

1. Flash with **Particle: Flash application (local)**

## Run

Before starting ingestion make sure you have an Edge Impulse account. Go to [edgeimpulse.com](http://edge-impulse.com) to sign up. And make sure you've created a project within Edge Impulse to create your ML model.

Connect your device to the Edge Impulse studio by running following command in a terminal:

```
$ edge-impulse-data-forwarder
```

After connecting, the tool will ask to login to your account and select the project. Lastly the tool will ask you name the axes you're about to sample. For a 3 axes accelerometer we would usually name them: `accX, accY, accZ`.

Now head over to Edge Impulse studio and start collecting data. More info on how to collect data can be found on the [docs pages](https://docs.edgeimpulse.com/docs/edge-impulse-studio/data-acquisition).
