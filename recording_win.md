# Recording Audio and Baseband (Windows)

1. Tune to the signal you would like to record, the same way you would tune to listen to the signal. For example, to record NOAA-18’s APT transmission, tune to `137.912.500`, i.e. 137.9125 MHz.
2. From the `≡` menu, open the “Recording” tab.
-  To record audio,
    1. Check the `Audio` box, and uncheck the `Baseband` box.
    2. Set `Sample Format` to “16 Bit PCM”.
    3. Click on `Record` to start recording. The button should turn into `Stop`.
    4. When finished, click on `Stop` to stop the recording.
    
- To record baseband, that is, the original signal spectrum received,

    1. Check the `Baseband` box, and uncheck the `Audio` box.

    2. Set `Sample Format` to “8 Bit PCM”.

        > The RTL-SDR produces 8-bit samples so it only wastes disk space to record samples with more bits. As an analogy, if you made a set of measurements with 2 decimal places, it wouldn’t help to write them down each with 4 decimal places.

    3. Click on `Record` to start recording. The button should turn into `Stop`.

    4. When finished, click on `Stop` to stop the recording.

## Reducing the file size of baseband recordings

SDR# can only record files up to 4 GiB in size, and this limit can be quickly reached when using one of the higher sample rates. Assuming 8-bit PCM as the sample format, the following table lists the maximum recording lengths for some “standard” RTL-SDR sample rate found in SDR#.

| Sample rate | Maximum recording length with SDR# recorder |
| ----------- | ------------------------------------------- |
| 2.88 MS/s   | 12 min 25 s                                 |
| 2.4 MS/s    | 14 min 54 s                                 |
| 2.048 MS/s  | 17 min 28 s                                 |
| 1.024 MS/s  | 34 min 57 s                                 |
| 250 kS/s    | 2 h 23 min 9 s                              |

