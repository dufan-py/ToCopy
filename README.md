# ToCopy


1. In the terminal, type command: **gh auth login**

2. In the terminal, type the following commands: 
**gh repo clone Fall24-Lab-EECS149-249a/lf-3pi-dufan-py**

    **cd lf-3pi-dufan-py**

https://www.lf-lang.org/embedded-lab/Sensors.html (3.4 ls dev/ttyACM*)


tinyurl.com/24-149lab0


proj1 doc: https://docs.google.com/document/d/1wJozeWa6TKpmjZbWJ9P1M-wfDc4eT2cJVSWn8u27-ls/edit


 target C {
    platform: {
      name: "rp2040",
      board: "pololu_3pi_2040_robot"
    },
    //single-threaded: false
  }
  import LED from "lib/LED.lf"

  preamble {=
    #include <stdio.h>
    #include <pico/stdlib.h>
    #include <hardware/gpio.h>
  =}
  
  main reactor {
    timer change(0, 250 ms)
    state led_on: bool = false
    L =new LED()
    reaction(startup) {=
      gpio_init(PICO_DEFAULT_LED_PIN);
      gpio_set_dir(PICO_DEFAULT_LED_PIN, GPIO_OUT);
    =}
  
    reaction(change) {=
        self->led_on = !self->led_on;
        //rintf("LED State: %b\n", self->led_on);
        If_set(set,self->led_on)
    =}
 
  }




  target C {
    platform: {
      name: "rp2040",
      board: "pololu_3pi_2040_robot"
    },
    single-threaded: true
  }
  preamble {=
    #include <hardware/gpio.h>
    #include <stdio.h>
    #include <pico/stdlib.h>
  =}
  reactor LED {
    input set:bool;
    
    reaction(startup) {=
      gpio_init(PICO_DEFAULT_LED_PIN);
      gpio_set_dir(PICO_DEFAULT_LED_PIN,GPIO_OUT);
    =}
  
    reaction(set) {=
      gpio_put(PICO_DEFAULT_LED_PIN,set)
    =}
  }
  
