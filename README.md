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

python3 -m venv .venv
source .venv/bin/activate
python3 -m pip install -r requirement.txt
