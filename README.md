# Sunglasses Detection on Sony IMX500

This repository contains the trained model and deployment files for a
sunglasses detection system running on the Sony IMX500 Intelligent Vision Sensor.

The project demonstrates an end-to-end edge AI workflow including
model training, quantization, packaging, and real-time inference
on embedded hardware.

---

## Project Overview

The goal of this project is to detect whether a person is wearing sunglasses
or not using an object detection model deployed directly on the IMX500 sensor.
All inference is performed on the sensor, minimizing latency and reducing
data transfer to the host system.

---

## Classes

The model detects the following classes:

- sunglasses
- without_sunglasses

---

## Repository Structure

deployment/
 ├── network.rpk
 ├── labels.txt
 └── README.md

---

## Deployment Files

- network.rpk  
  Packaged neural network model for the Sony IMX500 sensor.

- labels.txt  
  Class label definitions used by the model.

---

## Hardware Platform

- Raspberry Pi
- Sony IMX500 Intelligent Vision Sensor

---

## Running the Model

Example command using the Picamera2 IMX500 object detection demo:

python imx500_object_detection_demo.py \
  --model network.rpk \
  --labels labels.txt \
  --threshold 0.1 \
  --bbox-normalization \
  --bbox-order xy

---

## Notes

- The model is quantized to INT8 for efficient execution on the IMX500 sensor.
- Detection threshold may require tuning depending on lighting conditions.
- This repository contains deployment artifacts only.

---

## License

This project is provided for academic and educational purposes.
