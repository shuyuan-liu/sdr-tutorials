# Installing Basic Software (Linux) – SDR++

[SDR++](https://github.com/AlexandreRouma/SDRPlusPlus) is a relatively new SDR program written mainly by Alexandre Rouma. Its GitHub page, linked above, contains clear instructions for installing the software on Debian (and Ubuntu) and Arch Linux from a precompiled package. The instructions to compile from source however are slightly less clear, so this page will only document how to compile SDR++ from source.

## Tools and Dependencies

The following programs are needed to compile SDR++:

- A C++ compiler, for example g++
- CMake and Make to control the compilation process

Additionally, SDR++ makes use of the following libraries:

- [FFTW](https://fftw.org/) 3, for decomposing an incoming baseband signal into frequency components seen on the spectrum and waterfall displays
- [GLFW](https://www.glfw.org/) and [GLEW](http://glew.sourceforge.net/), to make use of OpenGL for faster rendering
- [VOLK](https://wiki.gnuradio.org/index.php/Volk), for accelerated mathematical operations
- [RtAudio](https://www.music.mcgill.ca/~gary/rtaudio/) for audio output
- [rtl-sdr](https://osmocom.org/projects/rtl-sdr/wiki/Rtl-sdr) to access data from RTL-SDR devices

Also, [Git](https://git-scm.com/) is required to fetch and later update SDR++‘s source code from GitHub.

The following command will install all of the above on a Debian-based (and thus Ubuntu) system:

```
sudo apt install g++ make cmake libfftw3-dev libglfw3-dev libglew-dev libvolk2-dev librtaudio-dev librtlsdr-dev git
```

## Download the Source

In a directory of your choosing, use the command `git clone https://github.com/AlexandreRouma/SDRPlusPlus.git` to download SDR++‘s source files. They will be placed in a folder named `SDRPlusPlus` in the current directory.

## Choose which modules to build

SDR++ is made up of multiple modules, including Sources that pull data from your SDR device, a Radio to demodulate transmissions, a Recorder to record audio and baseband, a Frequency Manager, and so on. We won’t need all of these modules, and in particular we don’t need any source modules apart from the RTL-SDR source. For a list of available modules, take a look at the #Sources, #Sinks, #Decoders and #Misc sections in `CMakeLists.txt`, or consult [this table](https://github.com/AlexandreRouma/SDRPlusPlus#module-list) on the GitHub page.

Here we will go for a minimal installation with only the most commonly used modules enabled. If at a later date you need a module that wasn’t built, simply repeat these steps but with that module set to `ON`, appended the cmake command below.

Enter the `SDRPlusPlus` directory, `mkdir build` and `cd build`. Then,

```
cmake -DOPT_BUILD_AIRSPY_SOURCE=OFF -DOPT_BUILD_AIRSPYHF_SOURCE=OFF -DOPT_BUILD_HACKRF_SOURCE=OFF -DOPT_BUILD_SOAPY_SOURCE=OFF -DOPT_BUILD_SPYSERVER_SOURCE=OFF -DOPT_BUILD_PLUTOSDR_SOURCE=OFF -DOPT_BUILD_NETWORK_SINK=OFF -DOPT_BUILD_WEATHER_SAT_DECODER=OFF -DOPT_BUILD_DISCORD_PRESENCE=OFF -DOPT_BUILD_RIGCTL_SERVER=OFF ..
```

Once the options are set, we can Make the program. It is recommended to let Make compile multiple files in parallel to speed up the process, and usually the number of parallel compilations is set as the number of CPU cores on the computer, so that each core handles the compilation of one source file at any time. In the command below, replace N with the number of cores in your processor:

```
make -jN
```

Once finished, test that SDR++ opens by running `./sdrpp`. If SDR++ opens and looks alright, you can install SDR++ so that it can be accessed from your desktop’s applications menu:

```
sudo make install
```

It might take a few seconds to show up in the menu. You’ve now compiled and installed SDR++ from source!

