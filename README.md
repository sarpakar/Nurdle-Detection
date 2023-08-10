# Nurdle Detection using YOLOv8 for Marine Ecology Conservation

This readme accompanies a project developed by a dedicated student team at Eindhoven University over the course of several years. It stands as a testament to their innovation and technical skills. Please note that this project is not associated with any specific course. Explore this repository for insights into the project's objectives, methods, and accomplishments.

# 1. Introduction

<div style="text-align: justify"> 
This is an unofficial report that explores the research and findings that had been conducted by the student team "Nurdle Soup" in Eindhoven University. The central objective was to develop an innovative method capable of utilizing AI technologies to track and detect nurdles. The paper presents an intelligent approach utlizing previously trained networks such as YOLOv8 in order to create a system of autonomly tracing plastic nurdles in marine environments. 
</div>

## 1.1. Paper summary

<div style="text-align: justify"> 
Super-resolution is enhancing the spatial resolution of a given image. Super-resolution networks are usually trained in a self-supervised manner in which low resolution (LR) images are generated from high resolution (HR) images by downsampling the HR image with a kernel (usually bicubic with anti-aliasing) then adding an additive gaussian noise. However, this degradation might not be ideal, and can perform poorly on real images. This situation stems from the domain gap between bicubically downsampled synthetic images and real images. 

<div style="text-align: center">

$I_{LR}$ = ($I_{HR}$ $\otimes$ k) + n

</div style>

Some researchers try to find the degradation kernel inside from the image (blind-SR)[1]. On the other hand, some researchers do not use kernels at all, and construct a new "real-world" dataset using cameras with different focal lengths [2]. Then, the network is trained in a supervised manner. Some other researches propose finding a kernel that minimizes the domain gap [3]. Domain translation methods are used here to map the bicubically downsampled images domain to the real images domain. GAN based methods are utilized here, but they are hard to train/converge. The winner of the AIM Challange on Real World SR at ICCV 2019 [4] proposes a method that uses adversarial loss only on the high-frequency data to speed-up convergence since low-frequency data can readily be obtained using the bicubically downsampled image. "Frequency Consistent Adaptation for Real World Super Resolution" paper is very close related to this paper. Here, authors also claim that downsampling using the bicubic kernel changes the frequency density distribution of the image as seen in Figure 1. To narrow the frequency density response gap between domains, they propose a frequency consistency loss. Using this loss alongside the wavelet loss (again only on high frequencies) they try to find a "frequency consistent" mapping between LR and HR images.
