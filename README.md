# Table of Contents
- [Download](#download)
- [Instructions](#instructions)
- [Prerequisites Hardware](#prerequisites-hardware)

# Download
## Download Windows .exe
Download [batflight3d.exe v1.0](https://github.com/christofhapp/batflight3d/releases/download/v1.0/batflight3d.exe).

## Download minimal working example
The [minimal working example](https://github.com/christofhapp/batflight3d/releases/download/v1.0/minimal_working_example.zip) contains data to try the software with a working data set. It is used in the instructions and helps to get used to the software before generating your own data.

# Instructions
The software is GUI based and looks like this:

![](images/overview_labeled.png)

## Workflow A: Calibration of the Camera System
For the calibration of the camera system follow the steps in this section. All steps are based on a minimal example, but work the
same with your own data.

### Load images
- Load the images by clicking on the **Load Images...** button.
- Navigate to the folder **calibration flight** of the minimal example and choose the folders **cam1, cam2** and the **imagelist.csv**.
You should now be able to see the first imagepair. Below the images you can find some helpful tools including pan, zoom and reset.
Use the image slider to navigate through the images.
If you move the slider, yellow or orange circles may appear. These points are detected by 2D detection and may be the drone, flying animals or distortions.

### Load drone points
The DJI drone log file (containing the flightpath) is also located in the minimal examples **calibration flight** folder. We first need to
decode and save it:

- menu: **Drone Points &rarr; decode DJI .TXT and save as .CSV**
- Choose file **DJIFlightRecord 2022-06-23 [21-42-26].txt** and save it as **DRONE_PTS.csv** in the same folder.
- Open **DRONE_PTS.csv** by clicking on the button **DRONE_PTS**
The button turns green when the drone points are loaded. If you want to ook at the drone flightpath, you can 3D plot it:
- menu: **3D Plot &rarr; 3Dplot ALL drone points**

### Choose drone points for a preliminary synchronization of the drone and camera signal
You now want to choose about 5 to 8 drone points for a preliminary synchronization. The drone points should not be very close together, so move the slider a good bit in order to get well distributed drone points. If you find a good image pair where you can identify the drone in the yellow circles, double click it in both images and they turn green. A window opens to show you how much points you have added already.

## Prerequisites Hardware
For the 3D reconstruction of flying animals with 3D Animal Flight Detector time synchronized images of two cameras are needed
as well as a drone flight log of a flight in front of the cameras. The points of the drone flight should be as evenly distributed in the sensed volume as possible.

### Cameras
The two Cameras have to be time synchronized and each image pair needs one timestamp. Place the images of the fi rst camera
in a folder and name the images alphanumerically (1.png, 2.png, ...). Do the same for the second camera with the same amount
of images and the same names. Also place an imagelist.csv with the timestamps at which each imagepair was taken:

```bash
project
├── cam1
│   ├── 1.png
│   ├── 3.png
│   ├── 5.png
│
├── cam2
│   ├── 1.png
│   ├── 3.png
│   ├── 5.png
│
├── imagelist.csv
```

imagelist.csv
```
nr,datetime
1, 2022-06-23 21:41:58.701641
3, 2022-06-23 21:42:02.034981
5, 2022-06-23 21:42:05.368321
```

### Drone Log File
A drone log file is needed with a timestamp, the latitudes and longitudes in the decimal form and the height above ground in
meters:

DRONE_PTS.csv
```
datetime,lat,lon,height
2022-06-23 19:42:26.386,49.42217084716835,11.447858470221677,0.0
2022-06-23 19:42:26.486,49.42217088440474,11.447858501829796,0.0
2022-06-23 19:42:26.586,49.42217094773711,11.447858540094895,0.0
```
