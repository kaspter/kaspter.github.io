---
layout: post
title: "uboot SPL Overview"
tagline: ""
description: ""
category: 
tags: [uboot]
---
{% include JB/setup %}

## Introduction

The idea is to build a mini u-boot(same as UBL in Davinci?) out of the u-boot tree that fits into SoC's internal SRAM (<=64K) and bootloads the real u-boot into the SDRAM, then the real u-boot will load the kernel into the SDRAM and boot it. :-).


## Duty of SPL

1> Basic ARM initialization

2> UART console initialization

3> Clocks and DPLL locking (minimal)

4> SDRAM initialization

5> Mux (minimal)

6> BootDevice initialization(based on where we are booting from.MMC1/MMC2/Nand/Onenand)

7> Bootloading real u-boot from the BootDevice and passing control to it.


BTW:

TI's X-loader is just one implemention of SPL out of the u-boot tree, And it depends on the u-boot source tree. same framework with u-boot. The u-boot guys will implement their own SPL in the tree. and then our system will boot without x-loader's help. :-)


## Reference

[u-boot maillist](http://lists.denx.de/pipermail/u-boot/) http://lists.denx.de/pipermail/u-boot/
