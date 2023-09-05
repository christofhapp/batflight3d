# Download Windows .exe
Download [batflight3d.exe v1.0](https://github.com/christofhapp/batflight3d/releases/download/v1.0/batflight3d.exe).

# Download minimal working example
The [minimal working example](https://github.com/christofhapp/batflight3d/releases/download/v1.0/minimal_working_example.zip) contains data to try the software with a working data set. It is used in the instructions and helps to get used to the software before generating your own data.

# Instructions
## Workflow A: aslkdfj
For the calibration of the camera system follow the steps in this section. All steps are based on a minimal example, but work the
same with your own data.

BUTTONS:
![](/buttons.PNG)
ENDE
![](https://christofhapp.lima.zone/wp-content/uploads/2023/09/slider-1024x451.png)

### Load images
Load the images by clicking on the Load Images... button:

Navigate to the folder calibration fl ight of the minimal example and choose the folders cam1, cam2 and imagelist.csv.
You should now be able to see the fi rst imagepair. Below the images you can fi nd some helpful tools including pan and zoom.
Below you fi nd a slider to navigate through the images:

### Load drone points


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
