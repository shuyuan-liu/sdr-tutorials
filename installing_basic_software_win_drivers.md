# Installing Basic Software (Windows) – Drivers

1. Plug the RTL-SDR into a free USB port on your computer.
2. Download Zadig from https://zadig.akeo.ie/. This program will install the driver needed to use your RTL-SDR. It’s required to install drivers because the RTL-SDR was originally made as TV receivers, so Windows identifies our dongle as such and by default will give it drivers for TV; we need a different driver to use the dongle as an SDR.
3. Open the downloaded file. A prompt will appear asking whether you want to allow Zadig to make changes to your device. Verify that the publisher displayed is “Akeo Consulting”; if not, delete the file, download it again, and retry this step.
4. Zadig should now open. In the `Options` menu, check `List All Devices`, because the SDR isn’t listed by default.
5. In the drop-down box below, select `Bulk-In, Interface (Interface 0)`. In some cases this is instead shown as `RTL2832UHIDIR` or `RTL2832U`. Then, verify that the `USB ID` shown below is `0BDA` `2838`. It is important that you choose the correct device because if the driver is installed to the wrong device then that device will probably stop working, and it can be a pain to get it back to normal.
6. Click on the large `Replace Driver` button, and wait for the process to finish.

