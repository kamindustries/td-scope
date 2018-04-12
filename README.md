# td-scope

td-scope is a flexible oscilloscope for TouchDesigner. It works in a similar way to a real oscilloscope: a trigger and slope direction tell the system what part of the signal to track. In this example, the sample's index that meets this trigger condition is passed to a vertex shader which shifts the whole graph to align it for rendering.

Built with TouchDesigner 099

### Usage

Connect an audio buffer to the td-scope tox and start adjusting parameters. Depending on how complex the signal is, some fine tuning of the trigger, comparator, and slope sign will be required to get a good track.

There's a little visual feedback thrown on at the end to make it look cool.

Tip: for particularly tricky signals, try using `Proximity` with a very small width.

### Parameters

`Latch` enables tracking to get a stable looking waveform. Turning it off makes it behave like a Trail CHOP and can be useful for longer timebases.

`Timebase` chooses the window size in stepped increments. The length in seconds is displayed in the disabled parameter above.

`Trigger` is the threshold at which the oscilloscope latches onto a signal. This has the largest influence on the waveform stability. It is normalized to the incoming signal. 

`Trigger Comparator` selects whether the oscilloscope should look for values greater than or less than the chosen trigger value. 
    
* `Less` latches onto values that are less than the trigger.   
* `Greater` latches onto values that are greater than the trigger.
* `Proximity` latches onto values that are within a certain range from the trigger. The `Trigger Width` parameter sets how large the acceptable range is.

`Slope Sign` pairs the trigger to either a positive or negative slope.

`Resample High Freq` will resample the buffer when the timebase is small (less than the length of 1 frame).

`Normalize Scale` normalizes the scope's vertical size.

`Scale` is a manual x/y scale on the visualization, applied after normalizing.

`Position` moves the graph horizontally and vertically.

### TODO

* Better centering
* Faster method of getting sample index. C++ CHOP?