# up to 6-AXIS-USBCNC-GRBL
This repository is based on [usbcnc grbl](https://github.com/usbcnc/grbl) which in turn is based on [native grbl 1.1f](https://github.com/gnea/grbl)<br>
With 6-AXIS-USBCNC-GRBL you can use 3,4(default),5 or 6 axis depend on definition in config.h
<img width="842" alt="stm32f103-usbcnc-pinout" src="https://user-images.githubusercontent.com/8062959/50537633-57946b80-0b73-11e9-92f8-e4ee15e2e923.png"><br>
Also there are some bugs (from usbcnc grbl) were fixed and some improvements were done.
Some of them:
- migrate from coIDE to Atollic truestudio
- 4,5,6th axis were added
- uint16_t probe_invert_mask
- [issue#36](https://github.com/usbcnc/grbl/issues/36) from usbcnc
- [issue#38](https://github.com/usbcnc/grbl/issues/38) from usbcnc
- [issue#41](https://github.com/usbcnc/grbl/issues/41) from usbcnc
- [issue#46](https://github.com/usbcnc/grbl/issues/46) from usbcnc
- [issue#40](https://github.com/usbcnc/grbl/issues/40) from usbcnc
- [issue#49](https://github.com/usbcnc/grbl/issues/49) from usbcnc
- NEW: STP_DRIVERS_ENABLE_DELAY
- [issue#48](https://github.com/usbcnc/grbl/issues/48) from usbcnc. STEP_PULSE_DELAY now works
- GPIO_PinRemapConfig(GPIO_Remap_SWJ_JTAGDisable, ENABLE); // to enable PA15, PB3, PB4 pins
- NEW: USE_RESET_BTN_AS_ESTOP
- improved performance and stability in stepper.c [issue#48](https://github.com/usbcnc/grbl/issues/48) from usbcnc
- [issue#60](https://github.com/usbcnc/grbl/issues/60) from usbcnc
- [issue#61](https://github.com/usbcnc/grbl/issues/61) from usbcnc

Before homing "error:7" appears 2 times due to startup blocks are empty. It's ok.
To eliminate this: set the startup blocks or comment definition in config.h

## Get started
- Install Atollic truestudio
- add this project to Atollic
- (<b>optional!</b>) configure grbl with config.h (<b>4 axis by default</b>. You can't change it through the grbl interface) and default.h (you can change this settings later throught the grbl interface)
- (<b>optional!</b> do this if you did the previous step) compille it
- use [st-link v2](https://www.st.com/content/st_com/en/products/development-tools/hardware-development-tools/development-tool-hardware-for-mcus/debug-hardware-for-mcus/debug-hardware-for-stm32-mcus/st-link-v2.html#design-scroll) or China clones for downloading firmware to [bluepill](http://wiki.stm32duino.com/index.php?title=Blue_Pill)
- configure grbl with "$x=val" commands (optional)
- use grbl controller with [UGS](https://winder.github.io/ugs_website/), [GcodeSender
](https://github.com/OttoHermansson/GcodeSender/downloads), [OpenCNCPilot
](https://github.com/martin2250/OpenCNCPilot) or other interfaces.
<br>

- You can also use UART (TX1, RX1) instead of USB to connect grbl controller via bluetooth and use with android app ["Grbl Controller"](https://play.google.com/store/apps/details?id=in.co.gorest.grblcontroller&hl=ru). Just #undef USEUSB in grbl.h after #ifdef STM32F103C8 or delete "USEUSB" in project properties -> C/C++ General -> Path and Symbols -> Symbols.
- If you want to use UART and more then 4 axis, you can map "B" axis Step and Dir outputs to PA11,12 instead of PA9,10 (see cpu-map.h).
- Don't map any pins if not sure. Some of them use microcontroller hardware features which aren't available on the other ones. 
