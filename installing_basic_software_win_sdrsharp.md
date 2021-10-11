# Installing Basic Software (Windows) – SDR#

Prerequisite: Install USB drivers for the RTL-SDR.

1. Go to https://airspy.com/download/ and download both the “SDR# Pre-requisites” and “Software Defined Radio Package”.

    > Besides the popular software SDR#, Airspy also makes excellent SDR hardware like the Airspy R2 and Mini.

2. Open the downloaded “dotnet-sdk-5.0.401-win-x86.exe” (perhaps with a higher version number), click on `Install` and follow through to the end of the process.

3. Unzip the contents of “sdrsharp-x86.zip” into an empty folder named e.g. “SDR#” or “SDR Sharp”. The name of this folder doesn’t affect anything; just that in my opinion “sdrsharp-x86” would look less pleasant.

4. Enter the folder and find “install-rtlsdr.bat”. Right-click on it and select `Edit`. A Notepad window will open showing the contents of the script. Delete the section beginning with `echo Downloading Zadig` down to `httpget ... zadig.exe`.

    > The reason for this is that 1) the script fetches an older version of Zadig than the one we did, and 2) we have already finished using Zadig so there’s no need to let the script download it again. 

    Save the file and close Notepad.

5. Now double-click on “install-rtlsdr.bat” to run it. It will now download a few files that enables SDR# to talk to the RTL-SDR.

6. Open “SDRSharp.exe”. The AIRSPY logo should appear and in a few seconds SDR# should have booted up.

7. Click on the `≡` button at the top-left of SDR#, and select `Source` in the list that appears. A “Source” tab should appear along the left edge of the SDR# window. “Source” lets you tell SDR# what kind of SDR you are using, e.g. RTL-SDR, Airspy, etc. Here we select “RTL-SDR USB”, since our dongle is connected via USB.

    > RTL-SDR TCP is for connecting to an RTL-SDR over the network instead of plugged into a USB port on your computer. This is useful for example if you want to place your SDR near an antenna on the roof but would like to use SDR# downstairs.

8. Click on the `⚙️` button to the right of `≡`. In the window that pops up, verify that “R820T” is shown at the top-right corner, and the drop-down box below is not empty, showing “Generic RTL2832U OEM” or something similar. Close the window.

9. Click on the `▶` button next to `≡`. You should be seeing something in the spectrum and waterfall displays and hearing sound from your speakers!