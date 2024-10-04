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
    platform: {
      name: "rp2040",
      board: "pololu_3pi_2040_robot"
    },
    single-threaded: true
  }
  
  preamble {=
    #include <stdio.h>
    #include <pico/stdlib.h>
    #include <hardware/gpio.h>
    #include<math.h>
  =}
  
  reactor AcceCDegree{
    input x:float
    input y:float
    input z:float
    output xDegree:float
    output yDegree:float
    output zDegree:float
  
    reaction(x,y,z)->xDegree,yDegree,zDegree {=
      lf_set(xDegree,acos(x->value)*180/M_PI);
      lf_set(zDegree,acos(z->value)*180/M_PI);
      lf_set(yDegree,acos(y->value)*180/M_PI);
    =}
  }

  
