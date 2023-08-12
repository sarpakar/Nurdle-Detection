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

* Raman spectroscopy, AFM-Infrared, and modified gas chromatography techniques are other microscopic methods used. However, there's a potential for scalability with Flow Cytometry, even though it's typically used for blood cell analysis. The concept of using its working principle for microplastic detection holds promise.

Ultimately, the use of image detection with cameras emerged as a more reasonable option.

## Documentation

See below for a quickstart installation and usage example

<details open>
<summary>Install</summary>



```python
!pip install ultralytics
!pip install labelme2yolo
import torch
from google.colab import drive
from ultralytics import YOLO
drive.mount("/content/gdrive")
```

```python
print('torch %s %s' % (torch.__version__, torch.cuda.get_device_properties(0) if torch.cuda.is_available() else 'CPU'))
```

</details>



<details open>
<summary>Usage</summary>

#### Data Preparation

converts labelme labels into coco format and splits the data into train validation, and test directories 
```python
!labelme2yolo --json_dir ./Images_and_Label --val_size 0.15 --test_size 0.15
```


#### CLI

YOLOv8 may be used directly in the Command Line Interface (CLI) with a `yolo` command:

```bash
!yolo task=detect mode=predict model= best.pt source = ./Footage/10049782_20170313_RCC.PNG save = True
```

#### Python

```python
model = YOLO("yolov8n.pt")
model.train(data="dataset.yaml", epochs = 100)
model.val()
model.export(format="onnx")
```

</details>

## <div align="center">Models</div>


