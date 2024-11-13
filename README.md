# ToCopy


1. In the terminal, type command: **gh auth login**

2. In the terminal, type the following commands: 
**gh repo clone Fall24-Lab-EECS149-249a/lf-3pi-dufan-py**

git clone http...

    **cd lf-3pi-dufan-py**
4. create a new branch and switch to it **git checkout -b lab<x>**, 已有分支：git checkout lab
5. push back  **git add .**


      **git commit -m "message"**

   
      **git push origin lab<x>**

   
https://www.lf-lang.org/embedded-lab/Sensors.html 


tinyurl.com/24-149lab0


proj1 doc: https://docs.google.com/document/d/1wJozeWa6TKpmjZbWJ9P1M-wfDc4eT2cJVSWn8u27-ls/edit


https://classroom.github.com/a/03KlHsiw


python3 detect.py --source 'libcamerasrc ! video/x-raw,width=640,height=480,framerate=30/1 ! videoconvert ! videoscale ! appsink' --weights yolov5s.pt --conf 0.25



rpicam-vid -t 10000 --codec libav --libav-format mp4 -o ~/Desktop/video.mp4


[1:50:48.948943913] [7289]  INFO Camera camera_manager.cpp:325 libcamera v0.3.2+27-7330f29b
[1:50:48.964966067] [7292] ERROR V4L2 v4l2_device.cpp:351 'imx477 10-001a': Unable to set controls: Device or resource busy
[1:50:48.993984928] [7292]  WARN RPiSdn sdn.cpp:40 Using legacy SDN tuning - please consider moving SDN inside rpi.denoise
[1:50:48.996692879] [7292]  INFO RPI vc4.cpp:447 Registered camera /base/soc/i2c0mux/i2c@1/imx477@1a to Unicam device /dev/media1 and ISP device /dev/media2
[1:50:48.996830674] [7292]  INFO RPI pipeline_base.cpp:1126 Using configuration file '/usr/share/libcamera/pipeline/rpi/vc4/rpi_apps.yaml'
Made X/EGL preview window
[1:50:50.338254253] [7289]  INFO Camera camera.cpp:1003 Pipeline handler in use by another process
ERROR: *** failed to acquire camera /base/soc/i2c0mux/i2c@1/imx477@1a ***

