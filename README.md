nrf51822 build script under MacOSX
=================================

Usage:
1. make erase_all

2. make debug

3. make release

4. make flash

5. make pin-reset

6. make serial # will start screen as your terminal

7. make gdbserver # will start gdbserver (-LocalHostOnly)

8. make gdb # will start gdb and set breakpoint at main then start

Steps:
------
0. download and extract nRF51-SDK 6.0.0 and s110 softdevice 7.0.0 

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


note [1]: s110 7.0.0 and s110 6.0.0 has different memory layout, 7.0.0 uses 0x16000 as app location while 6.0.0 uses 0x14000, and the build scripts here support 7.0.0 only, if you want to use with 6.0.0. If you want to use 6.0.0, first change Makefile.common, find the STARTADDRESS and change the address, and replace all the .ld files with which included in nRF51-SDK 5.2.0)

note[2]: Currently JLink (for MacOSX) v4.90b will not require disabling CDC, highly recommend use that new version, that will allow use GDB and virtual com port simutaneously.
