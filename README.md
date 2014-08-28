nrf51822 build script under MacOSX
=================================

Usage:
------

1. install arm-none-eabi-gcc for MacOSX:

    from: https://launchpad.net/gcc-arm-embedded

2. create your project file

3. copy Makefile.template as Makefile to your project directory

4. modify Makefile variable to suit your environment

5. (optional) change Makefile.posix to suit your gcc version

6. make

7. make erase_all

8. make flash_softdevice

9. make flash

