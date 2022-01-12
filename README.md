# YOLOv4-object-detector-for-rats

![New video (1)](https://user-images.githubusercontent.com/97471111/149231411-6206fa0c-c302-4220-8de1-8d6924827c25.gif)


This model is trained with about 950 images containing closeup and distanced images of rats. 

To label the images, I used lablelImg to create .txt files for Yolo.

The yolov4-rat.cfg, obj.data, and obj.names files are edited for 1 class detection(rat). 
Filters are changed to 18. 

Training
```
darknet.exe detector train data/obj.data cfg/yolov4-rat.cfg yolov4.conv.137 -map
```
![chart](https://user-images.githubusercontent.com/97471111/149238345-d36fabf0-e9de-4160-8b7c-7eba8ca33b25.png)

Run on a video
```
darknet.exe detector demo data/obj.data cfg/yolov4-custom.cfg ../training/yolov4-rat_best.weights ../../videos/test.mp4 -thresh 0.5 -i 0 -out_filename ../../videos/rats.avi
```
![New 3 (2)](https://user-images.githubusercontent.com/97471111/149241278-d89116c1-58af-49f3-b431-6f15e3540b01.gif)


CUDA 10.1
OpenCV >= 4.1
cuDNN =8.0.5 for CUDA 10.1
Visual Studio 2019
CMake >= 3.12

# Reference
AlexeyAB GitHub
