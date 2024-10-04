# ToCopy


1. In the terminal, type command: **gh auth login**

2. In the terminal, type the following commands: 
**gh repo clone Fall24-Lab-EECS149-249a/lf-3pi-dufan-py**

    **cd lf-3pi-dufan-py**
3. create a new branch and switch to it **git checkout -b lab<x>**, 已有分支：git checkout lab
4. push back  **git add .**


      **git commit -m "message"**

   
      **git push origin lab<x>**

   
https://www.lf-lang.org/embedded-lab/Sensors.html 


tinyurl.com/24-149lab0


proj1 doc: https://docs.google.com/document/d/1wJozeWa6TKpmjZbWJ9P1M-wfDc4eT2cJVSWn8u27-ls/edit



 target C {
    platform: "RP2040",
    single-threaded: true
  }
  
  import AcceCDegree from "lib/Tilt.lf"
  import Accelerometer from "lib/IMU.lf"
  import Display from "lib/Display.lf"
  
  main reactor {
    a = new Accelerometer()
    d = new Display()
    c = new AcceCDegree()
    timer t(0, 250 msec)
  
    reaction(t) -> a.trigger {=
      lf_set(a.trigger, true);
    =}
    reaction(a.x, a.y, a.z)->c.x,c.y,c.z{=
        lf_set(c.x , a.x->value);
        lf_set(c.y , a.y->value);
        lf_set(c.z , a.z->value);
    =}


    reaction(c.xDegree, c.yDegree, c.zDegree) -> d.line0, d.line1, d.line2 {=
      /// TODO: define max string size for line
      /// based on font you can have 4 or 8 lines
      static char buf0[17];
      static char buf1[17];
      static char buf2[17];
      
      snprintf(buf0, 17, "x:%2.4f", c.xDegree->value);
      snprintf(buf1, 17, "y:%2.4f", c.yDegree->value);
      snprintf(buf2, 17, "z:%2.4f", c.zDegree->value);
  
      lf_set(d.line0, buf0);
      lf_set(d.line1, buf1);
      lf_set(d.line2, buf2);
    =}
  }
  
