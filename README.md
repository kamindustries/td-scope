# td-oscilloscope

td-oscilloscope is a compact and flexible oscilloscope for TouchDesigner. This repo contains the primary tox component as well as an example project, which simply hooks up an audio source to the tox.

Build with TouchDesigner 099

### Usage

Connect an audio buffer to the td-oscilloscope tox and start adjusting parameters. Depending on how complex the signal is, some fine tuning of the trigger, comparator, and slope sign will be required to get a good track.

Note there's a little visual feedback thrown on at the end to make it look cool.

### Parameters

`Latch` turns on oscilloscope tracking to get a stable looking waveform. Leaving it off can be useful for longer timebases.

`Timebase` chooses the window size in stepped increments. The length in seconds is displayed in the disabled parameter above.

`Trigger` is the threshold at which the oscilloscope latches onto a signal. This has the largest influence on the waveform stability. It is normalized to the incoming signal. 

`Trigger Comparator` selects whether the oscilloscope should look for values greater than or less than the chosen trigger value. 

`Slope Sign` matches the trigger to either a positive or negative slope.

`Normalize Scale` normalizes the scope's vertical size.

`Scale` is a manual x/y scale on the visualization, applied after normalizing.

`Resample High Freq` will resample the buffer when the timebase is small (less than the length of 1 frame).