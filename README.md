nrf51822 build script under Linux and MacOSX
============================================

Notes:
-----

    This HEAD revision has been updated for nRF51 SDK 9.0.0 Softdevice 8.0.0.

    If you need prior to nRF-SDK 6.x, please use branch nrf51sdk6.x

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
0. download and extract nRF51-SDK 9.0.0 (now SDK has included hex file of softdevice 8.0.0)

1. install arm-none-eabi-gcc for Linux or MacOSX: (4.9-2015q3)

    from: https://launchpad.net/gcc-arm-embedded

2. create your project file

3. a. copy Makefile.config.template as Makefie.config to some directory, and change its directories accordingly.

   b. copy Makefile.template as Makefile to your project directory

4. modify Makefile variable to suit your environment, and include correct Makefile.config

5. make (make debug or make release)

6. make erase_all

7. make flash_softdevice

8. make flash

note[1]: OpenOCD supported (0.9-trunk advised) if you set FLASHER as OpenOCD at Makefile.common file. You also need to adjust $OPENOCD command for your OpenOCD compatible dongle at same file. You can also flash "softdevice 6.0" with OpenOCD flasher. PS: This patch increases OpenOCD speed by 10 ( http://openocd.zylin.com/#/c/2204/ )

note[2]: Currently JLink (for MacOSX) v4.90b will not require disabling CDC, highly recommend use that new version, that will allow use GDB and virtual com port simutaneously.

note[3]: Linux and OpenOCD support was submitted by https://github.com/EUA, if you have any problems please @him or create a issue on his https://github.com/EUA/nrf51822-posix-build-scripts
