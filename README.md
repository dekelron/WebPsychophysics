# WebPsychophysics
Time-accurate stimuli presentation for a web browser

All files are made available under a [CC BY-NC 4.0 International license](https://creativecommons.org/licenses/by-nc/4.0/).

The WebPsychophysics library was built to enable running time-accurate Psychophysical experiments on a web browser.
If you do not care about the time-accuracy of your stimuli, you may want to consider using [JsPsych](https://www.jspsych.org/) instead.
The WebPsychophysics library is implemented using Javascript and the WebGL technology. The library takes a pre-determined set of images, and timing information. The images are pre-loaded to the GPU, and presented when needed. This implementation permits nearly perfect single-frame time accuracy when hardware is adequate (and it usually is).

The library was built with experiments in mind.
The definition of the entire experimental structure is a JSON file.
The experiment is composed of a set of blocks, for example a practice block, followed by test block, and a questionnaire block.
Blocks such as the practice and the test are composed of "trials". A trial is a set of stimulus presentations and responses collection.
Each stimulus is an image, defined in the JSON file by an http link to the image file.
At the beginning of the experiment, all images from all trials are loaded to the RAM.
At the beginning of each trial, all trial images are loaded to the GPU.
During the experiment, all responses are collected. The timing diagnostics of all image presentations are collected as well. This results in a large JSON file (~1MB in long experiments), that can be sent to a server or saved on the computer.
You can parse a JSON file in most languages (MATLAB, Python), so you can treat the loaded data as if its just a native structure of the language.

Works well:
    (-) Fullscreen, gamma-corrected, alpha-blended, colored stimulus presentation.
    (-) Brief presentations (even <50 ms, but make sure to check the timing diagnostics).
    (-) Post-experiment surveys, custom html frames (for instructions).
    (-) Minor logic (feedback, repeat of blocks conditioned on accuracy).
Doesn't work well:
    (-) Movies.
    (-) Random dot kinematograms (RDK).
    
