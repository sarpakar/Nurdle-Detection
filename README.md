# Nurdle Detection using YOLOv8 for Marine Ecology Conservation

This readme accompanies a project developed by a dedicated student team at Eindhoven University over the course of several years. It stands as a testament to their innovation and technical skills. Please note that this project is not associated with any specific course. Explore this repository for insights into the project's objectives, methods, and accomplishments.

# 1. Introduction

<div style="text-align: justify"> 
This is an unofficial report that explores the research and findings that had been conducted by the student team "Nurdle Soup" in Eindhoven University. The central objective was to develop an innovative method capable of utilizing AI technologies to track and detect nurdles. The paper presents an intelligent approach utlizing previously trained networks such as YOLOv8 in order to create a system of autonomly tracing plastic nurdles in marine environments. 
</div>

## 1.1. Paper summary

<div style="text-align: justify"> 
In 2023, despite the year, 32% of plastic production continues to escape into nature, fragmenting into harmful particles over time. Notably, 200,000 tonnes of nurdles, tiny plastic pellets, infiltrate ecosystems annually, constituting a major microplastic pollution source. Nurdle Soup, formed by Eindhoven University students and a foundation, aims to combat this issue through self-developed intelligent plastic detection tech integrated into autonomous systems, aiding cleanup initiatives and encouraging pollution prevention. The project employs YOLOv8, an advanced object detection framework, to enhance the accuracy of plastic detection and contribute to our mission of safeguarding ecosystems.


* Various techniques are employed in the detection of microplastics, including visible light (microscopy), scanning electron microscopy, Fourier transform infrared spectroscopy (FTIR), Raman spectroscopy, and more. These methods often face challenges in terms of scalability due to their complex and equipment-intensive nature.

* Visible Light (Microscopy) is used based on microplastics' light, color, and shape, but it lacks accuracy and is subject to human dependence. Scanning electron microscopy, while powerful, is costly and not easily scalable due to its specialized equipment. FTIR, a standard technique for identifying synthetic polymers, is non-destructive but also operates on a microscopic scale, limiting its scalability.

## <div align="center">Documentation</div>

See below for a quickstart installation and usage example, and see the [YOLOv8 Docs](https://docs.ultralytics.com) for full documentation on training, validation, prediction and deployment.

<details open>
<summary>Install</summary>

Pip install the ultralytics package including all [requirements](https://github.com/ultralytics/ultralytics/blob/main/requirements.txt) in a [**Python>=3.8**](https://www.python.org/) environment with [**PyTorch>=1.8**](https://pytorch.org/get-started/locally/).

[![PyPI version](https://badge.fury.io/py/ultralytics.svg)](https://badge.fury.io/py/ultralytics) [![Downloads](https://static.pepy.tech/badge/ultralytics)](https://pepy.tech/project/ultralytics)

```bash
pip install ultralytics
```

For alternative installation methods including [Conda](https://anaconda.org/conda-forge/ultralytics), [Docker](https://hub.docker.com/r/ultralytics/ultralytics), and Git, please refer to the [Quickstart Guide](https://docs.ultralytics.com/quickstart).

</details>

<details open>
<summary>Usage</summary>

#### CLI

YOLOv8 may be used directly in the Command Line Interface (CLI) with a `yolo` command:

```bash
yolo predict model=yolov8n.pt source='https://ultralytics.com/images/bus.jpg'
```

`yolo` can be used for a variety of tasks and modes and accepts additional arguments, i.e. `imgsz=640`. See the YOLOv8 [CLI Docs](https://docs.ultralytics.com/usage/cli) for examples.

#### Python

YOLOv8 may also be used directly in a Python environment, and accepts the same [arguments](https://docs.ultralytics.com/usage/cfg/) as in the CLI example above:

```python
from ultralytics import YOLO

# Load a model
model = YOLO("yolov8n.yaml")  # build a new model from scratch
model = YOLO("yolov8n.pt")  # load a pretrained model (recommended for training)

# Use the model
model.train(data="coco128.yaml", epochs=3)  # train the model
metrics = model.val()  # evaluate model performance on the validation set
results = model("https://ultralytics.com/images/bus.jpg")  # predict on an image
path = model.export(format="onnx")  # export the model to ONNX format
```

[Models](https://github.com/ultralytics/ultralytics/tree/main/ultralytics/cfg/models) download automatically from the latest Ultralytics [release](https://github.com/ultralytics/assets/releases). See YOLOv8 [Python Docs](https://docs.ultralytics.com/usage/python) for more examples.

</details>

## <div align="center">Models</div>

* Raman spectroscopy, AFM-Infrared, and modified gas chromatography techniques are other microscopic methods used. However, there's a potential for scalability with Flow Cytometry, even though it's typically used for blood cell analysis. The concept of using its working principle for microplastic detection holds promise.

Ultimately, the use of image detection with cameras emerged as a more reasonable option.
