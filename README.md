# 6-AXIS-USBCNC-GRBL
This repository based on [usbcnc grbl](https://github.com/usbcnc/grbl) which in turn is based on [native grbl 1.1f](https://github.com/gnea/grbl)<br>
With 6-AXIS-USBCNC-GRBL you can use 3,4,5 or 6 axis depend of definition in config.h
Also there are some bugs (from usbcnc grbl) were fixed and some improvements were done.
Some of them:
- migrate from coIDE to Atollic truestudio
- 4,5,6th axis were added
- uint16_t probe_invert_mask
- [issue#36](https://github.com/usbcnc/grbl/issues/36)
- [issue#38](https://github.com/usbcnc/grbl/issues/38)
- [issue#41](https://github.com/usbcnc/grbl/issues/41)
- [issue#46](https://github.com/usbcnc/grbl/issues/46)
- [issue#40](https://github.com/usbcnc/grbl/issues/40)
- [issue#49](https://github.com/usbcnc/grbl/issues/49)
- NEW: STP_DRIVERS_ENABLE_DELAY
- [issue#48](https://github.com/usbcnc/grbl/issues/48) STEP_PULSE_DELAY now works
- GPIO_PinRemapConfig(GPIO_Remap_SWJ_JTAGDisable, ENABLE); // to enable PA15, PB3, PB4 pins
- NEW: USE_RESET_BTN_AS_ESTOP
- improved performance and stability in stepper.c [issue#48](https://github.com/usbcnc/grbl/issues/48)
- [issue#60](https://github.com/usbcnc/grbl/issues/60)
- [issue#61](https://github.com/usbcnc/grbl/issues/61)
