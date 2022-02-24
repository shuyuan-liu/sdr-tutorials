

**Please note this repo is under (not-so-active-due-to-university) construction, and there are many incomplete pages and links. I might add indicators at some point to show the status of each page.**

# Get Started Playing with Software Radio

Software radios, or software-defined radios (SDRs) differ from traditional radios in that computer software is used to do most of the signal processing instead of hard-wired circuitry. This allows an SDR receiver or transmitter to be flexibly modified and new features easily tested and added without needing to change its hardware.

Some of the “classic” things hobbyists can do with a receive-only SDR are listening to air traffic control, receiving weather satellite images, monitoring amateur radio contacts, and getting positioning information from aeroplanes.

## The RTL-SDR

The RTL-SDR is a family of cheap receive-only SDRs originally repurposed from RTL2832U-based DVB-T TV receivers (see [wiki page on Osmocom’s website](https://osmocom.org/projects/rtl-sdr/wiki/Rtl-sdr)). As one of the earliest SDRs cheap enough for popular use, they have a large community of users and great software support. The RTL-SDR has been redesigned by several companies for SDR usage, with popular ones such as the [RTL-SDR Blog V3](https://www.rtl-sdr.com/buy-rtl-sdr-dvb-t-dongles/) and the [Nooelec NESDR SMArt](https://www.nooelec.com/store/sdr/sdr-receivers/nesdr-smart-sdr.html) and [SMArTee](https://www.nooelec.com/store/sdr/sdr-receivers/nesdr-smartee-sdr.html). These are usually preferred over the original TV dongles for their better performance and . The improved models usually feature a more common SMA connector for the antenna instead of a TV or MCX connector; many have metal casing instead of plastic to shield it from external electrical noise; some can also deliver power to active antennas or preamplifiers that help increase received signal strength.

### Other Popular SDRs

There are also many popular SDRs based on chips other than the RTL2832U. The [HackRF One](https://greatscottgadgets.com/hackrf/one/) can both receive and transmit; the [Airspy R2](https://airspy.com/airspy-r2/) and [Airspy Mini](https://airspy.com/airspy-mini/) have higher sensitivity and are also less easily overpowered by strong, interfering signals; the Airspy HF+ and SDRPlay series can receive short wave and medium wave frequencies that are below the range of most other SDRs. All of the SDRs above except Airspy HF+ also have higher sampling rates, allowing a broader range of frequencies to seen on screen at a time than with an RTL-SDR.

Although there are the more advanced SDRs, in this set of tutorials we will use the RTL-SDR, since it is relatively cheap, well-supported, and already powerful enough for many purposes. Specifically, we will use the RTL-SDR Blog V3, for its low price, switchable bias-tee (power delivery though the antenna port), and direct sampling mode which allows reception in some HF bands. Once familiar with the RTL-SDR, it should be straightforward to switch to another model if more advanced features are needed.

## Table of Contents

Both Windows and desktop Linux setups are covered, however because Linux distributions use different package managers and package names, readers will need to adapt the Linux tutorials to their own systems. 

| Chapter                                                      | Windows                                                      | Desktop Linux                                                |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Installing basic software                                    | [USB drivers](installing_basic_software_win_drivers.md) and then [SDR#](installing_basic_software_win_sdrsharp.md) | [SDR++](installing_basic_software_linux_sdrpp.md) or [gqrx](./installing_basic_software_linux_gqrx.md) |
| Essential controls                                           | [SDR#]()                                                     | [SDR++]() or [gqrx]()                                        |
| [Making a V-dipole antenna](https://lna4all.blogspot.com/2017/02/diy-137-mhz-wx-sat-v-dipole-antenna.html) | —                                                            | —                                                            |
| APT from NOAA 15, 18, and 19                                 | [VB Cable](https://vb-audio.com/Cable/index.htm) and then [WXtoImg](https://wxtoimgrestored.xyz/) | [noaa-apt](https://noaa-apt.mbernardi.com.ar/) or [Xerbo/aptdec](https://github.com/Xerbo/aptdec) |
| LRPT from Meteor-M N2                                        | [Meteor Demodulator](), [M2 LRPT Decoder](), and [SmoothMeteor]() | [meteor_demod](https://github.com/dbdexter-dev/meteor_demod), [meteor_decode](https://github.com/dbdexter-dev/meteor_decode), and [meteor_rectifyCPP](https://github.com/TGYK/meteor_rectifyCPP) |

 
