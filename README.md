# QIDK Image Inpainting

This project implements AI-based image inpainting accelerated on Qualcomm NPUs. It features a complete Android application (`LamaInpaint`) and benchmarking scripts to evaluate inference performance.

## Overview

Image inpainting aims to reconstruct missing or masked regions in an image seamlessly. We leverage a high-performance inpainting model optimized for edge devices, taking advantage of Qualcomm Neural Network (QNN) libraries to run inference efficiently on the Neural Processing Unit (NPU).

## Components

1. **Android Application (`Code/LamaInpaint`)**
   - A fully functional Android app that lets users mask parts of an image and generate inpainted results on-device.
   - Integrated with Qualcomm's QNN SDK to hardware-accelerate model inference.
   
2. **Benchmarking Suite (`Code/qidk-benchmarking`)**
   - Scripts and tools for testing the throughput, latency, and quality of the inpainting model across different hardware targets (CPU vs NPU).
   - Includes a sample generator for robust testing.

3. **Scripts & Models (`Code/scripts`)**
   - Includes serialized model binaries (e.g., AOTGAN) optimized in FP16 for the NPU.

## Results & Benchmarks

The project demonstrates significant speedups when migrating from standard CPU inference to NPU execution, maintaining visual quality while drastically reducing inference latency and power consumption. Detailed logs and outputs are provided in the respective benchmarking directories.

## Building the Android App

```bash
cd Code/LamaInpaint
./pull_all_deps.sh
./copy_qnn_libs.sh
./gradlew assembleDebug
```