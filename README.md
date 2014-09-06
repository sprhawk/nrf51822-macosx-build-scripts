nrf51822 build script under Linux and MacOSX
============================================

Usage:
1. make erase_all

2. make debug

3. make release

4. make flash

5. make pin-reset

6. make serial # will start screen as your terminal. You need to adjust for your terminal program

7. make gdbserver # will start gdbserver (-LocalHostOnly)

8. make gdb # will start gdb and set breakpoint at main and app_error_handler then start

Steps:
------
0. download and extract nRF51-SDK 6.0.0 (or 5.1.0) and s110 softdevice 7.0.0 (or 6.0.0)

1. install arm-none-eabi-gcc for Linux or MacOSX:

    from: https://launchpad.net/gcc-arm-embedded

2. create your project file

3. copy Makefile.template as Makefile to your project directory

4. modify Makefile variable to suit your environment

5. (optional) change Makefile.posix to suit your gcc version

6. make

7. make erase_all

8. make flash_softdevice

9. make flash

note[1]: OpenOCD supported (0.9-trunk advised) if you set FLASHER as OpenOCD at Makefile.common file. You also need to adjust $OPENOCD command for your OpenOCD compatible dongle at same file. You can also flash "softdevice 6.0" with OpenOCD flasher. PS: This patch increases OpenOCD speed by 10 ( http://openocd.zylin.com/#/c/2204/ )

note[2]: Currently JLink (for MacOSX) v4.90b will not require disabling CDC, highly recommend use that new version, that will allow use GDB and virtual com port simutaneously.
