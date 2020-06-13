# Installation Notes

Purpose of this project is the get Blinky running on a Nordic Semiconductor development kit by compiling the project with Make.

Blinky is a program that continuously blinks a light emitting diode by turning it on off. It is the domain of embedded systems the equivalence of Hello world!

## Nordic SDK

Nordics's software development kit (SDK) version 16 was downloaded from [https://developer.nordicsemi.com/nRF5_SDK/](https://developer.nordicsemi.com/nRF5_SDK/)

## Reference Blog

This blog [Development with GCC and Eclipse](https://devzone.nordicsemi.com/nordic/nordic-blog/b/blog/posts/development-with-gcc-and-eclipse) was used as a reference.

## GNU Toolchain

The GNU Embedded Toolchain for Arm was downloaded from [developer.arm.com](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm/downloads).

The Windows 32-bit Installer was chosen due to that the project will start out on a PC with Windows 10.

In the installer so was Add path to environment variable manually ticked in, other settings left to default.

Tested the install with:

```console
arm-none-eabi-gcc --version
```

Did not work in the Windows power shell but worked in the ordinary terminal (cmd.exe) so hoping for the best at the moment.

## GNU Make

Had GNU Make installed already, would otherwise have to install this.

## SDK Setup

Edited the file makefile.windows in:

...\nRF5_SDK_16.0.0_98a08e2\components\toolchain\gcc

To have the following content:

```console
GNU_INSTALL_ROOT := C:/Program Files (x86)/GNU Arm Embedded Toolchain/9 2020-q2-update/bin/
GNU_VERSION := 9.3.1
GNU_PREFIX := arm-none-eabi
```

Notes on this is that the spaces seems ok but must use forward slashes and there shall also be a forward slash at the end.

## Compiling

Used the terminal command make to compile.

Result:

```console
mkdir _build
cd _build && mkdir nrf52832_xxaa
Assembling file: gcc_startup_nrf52.S
Compiling file: nrf_log_frontend.c
Compiling file: nrf_log_str_formatter.c
Compiling file: boards.c
Compiling file: app_error.c
Compiling file: app_error_handler_gcc.c
Compiling file: app_error_weak.c
Compiling file: app_util_platform.c
Compiling file: nrf_assert.c
Compiling file: nrf_atomic.c
Compiling file: nrf_balloc.c
Compiling file: nrf_fprintf.c
Compiling file: nrf_fprintf_format.c
Compiling file: nrf_memobj.c
Compiling file: nrf_ringbuf.c
Compiling file: nrf_strerror.c
Compiling file: nrfx_atomic.c
Compiling file: main.c
Compiling file: system_nrf52.c
Linking target: _build/nrf52832_xxaa.out
   text    data     bss     dec     hex filename
   2072     108      28    2208     8a0 _build/nrf52832_xxaa.out
Preparing: _build/nrf52832_xxaa.hex
Preparing: _build/nrf52832_xxaa.bin
DONE nrf52832_xxaa
```

So seems that got something called nrf82832_xxaa hex and bin.

## Flashing to hardware

Remains to flash the software to a PCA10040 development kit that I have.