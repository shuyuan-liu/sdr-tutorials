# Installing Basic Software (Linux) – Gqrx

[Gqrx](https://gqrx.dk/) is an SDR receiver program offering simpler controls than SDR# or SDR++. It has little signal decoding or noise removal functionality, and doesn’t support plugins either. However this lack of advanced functionality also means it could be easier to get started with.

Gqrx is built upon [GNU Radio](https://www.gnuradio.org/), a popular set of signal processing software “blocks” that can be combined, either in code or by using a graphical editor, to produce custom receivers and signal processors. Apart from building software like Gqrx, GNU Radio is also used by students and hobbyists to experiment with signal processing without heavy programming knowledge.

## Installing the rtl-sdr library

Gqrx needs the [rtl-sdr library](https://github.com/osmocom/rtl-sdr) to retrieve data from an RTL-SDR device. On Ubuntu, Debian and similar distributions, rtl-sdr can be installed with the command

```
sudo apt install rtl-sdr
```

## Installing Gqrx

Gqrx can be installed from a precompiled binary package in your Linux distribution’s software repository. On Ubuntu this con be done with

```
sudo apt install gqrx
```

## Test the install

