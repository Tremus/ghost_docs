# GHOST

Version 1.0

## Presets

### Preset format

Ghost presets are saved in using the JSON file extension `.json`. This is a popular human readable text format that is relatively simple for computer programs to read and write. Compared to other binary formats, json files tend to be a bit larger, however they are much easier to debug.

### Preset location

By default, Ghost searches for presets in the following location:

#### Windows

`C:\Users\{username}\Documents\exacoustics\GHOST`

#### macOS

`/Users/{username}/Music/exacoustics/GHOST`

# Navbar

### Hamburger menu:

-   Init
-   Load Preset
-   Save preset / Register
-   Check for updates

### Preset name

Opens the preset browser

Preset up/down buttons

### Level meter

Output in decibels for the left & right channel

Triangle controls the gain. This gain control can also be automated

### Oscilloscope

Shows audio output in mono. Intelligently detects the pitch of the acitve oscillator (A-B) in order to show what the waveform looks like.

## Registration

If you have not registered the synth, you will be greeted with a demo notification when you open a new window. To register, simply enter the email and password you used on exacoustics.com when you purchased Ghost.

When registering Ghost, you will need an active internet connection. If you have purchased the full license, you will only need an internet connection only _once_.

If you purchased Ghost through the rent to own plan, you will need an internet connection at least once a week while the plan is active. This is so Ghost can check the plan is still active or completed. If this fails for several weeks or the rent to own plan is paused, Ghost will revert to its demo state. Once the rent to own plan is completed, Ghost will detect this and remove the requirement of an internet connection.

If you accidently close this window before registering and need to access it again, you can show the window again by opening the hamburger menu in the navbar and clicking "Register". If Ghost is already registered, you cannot access this window.

## Saving presets

You can bring up the window for saving presets through the hamburger menu in the navbar, or by clicking on the floppy disk icon next to the preset name.

-   Preset name: Enter the name for your preset. The saved preset file will share the same name.
-   Artist: Enter your artist name. Ghost will remember the last saved artist name and pre-fill this field.
-   Choose folder: Choose a location on your computer to save the file
-   Tags: Set tags on your preset to help you find it later within the preset browser.

## Preset Browser

### Spinning wheel

This is a loading wheel which is displayed while your preset directory is being scanned and metadata is being read. Each time you open the preset browser all your presets are rescanned in order to keep your data up to date. This is a heavily optimised routine and tends to run very quickly, even with a really large folder of presets.

**_Note_**: On Windows, this process may take a bit longer than on macOS, especially if you have lots of presets. The reason for this slow down is that virus protection software such as Windows Defender intercepts the file reading to scan the preset file for malicious viruses. Presumably, the preset will not be infected with viruses, and the preset is suspected to be temporarily _whitelisted_ by Windows Defender for 20 minutes or thereabouts. While on this whitelist, rescans of all these presets will be lightning fast, with speeds similar to macOS.

If you use Windows Defender and this slow behaviour proves to be too slow and frustrating to you, _it is possible to speed things up_ by adding the `.json` file extension to the Windows Defender whitelist, but for potential security and legal reasons I will not go on record recommending it to you. You can look up how to do these things yourself if you're curious and like to live dangerously.

### Search

This performs a case insensitive search of the filenames within the currently selected folder and its subfolders.

### Folders

Select a folder to filter presets belonging to the selected folder or one of its subfolders. Additionally, if the folder contains subfolders, you can click the triangle button to the left of the folder name to expand the list and view its subfolders.

To disable filterting by folders, select "All files" at the top of the list.

### Tags

Filter the presets by its tag within the currently selected folder and its subfolders. Filtered items will contain _at least every selected tag_.

You can quickly clear all selected tags by clicking the "Clear tags" button placed right above the tags.

### Preset table

The table columns **Name**, **Artist** and **Tags** correspond to metadata within your saved preset. You can right click on these fields to edit them.

The **heart** icon on the left can be used for favouriting presets. A list of your favourites is saved locally, meaning the list will be unique to your device and cannot be transfered to another device.

If you select the heart within the table header, you will filter by favourited presets.

# Oscillator

### Osc buttons

There are 6 oscillators in GHOST. You can change the currently displayed oscillator by clicking on the buttons labelled A - F. All knobs and settings you see in this area (show picture) belong to each oscillator.

A single left click will display the wavetable belonging to that oscillator. All of the pitch controls, filter controls, distortion controls also belong to each oscillator, so their changes will be reflected when you switch.

### Save

Save the wavetable used by the active oscillator to a file. Supported formats are `.flac` and `.wav`.

### Wavetables

Ghosts oscillator engine use wavetables. A wavetable is small digital audio sample that when played back fast enough, can sound very similar to analogue synthesisers. A great advantage of using digital wavetables is that a much wider variety of sounds can be produced, and they can be processed in ways that would be almost impossible using hardware circuitry!

Ghosts wavetables use shapes consisting of exactly 2048 points, with a maximum of 256 shapes.

New wavetables can be easily imported by dragging audio files from your file window or DAW and dropping them over this area. Supported audio codecs include FLAC, WAV and AIFF. Wavetables generated by other software and downloaded from the internet will most likely be compatible.

By right cliucking on the wave shape, you can open up a menu with some useful functions:

-   Init: Resets the wavetable to the default consisting of a Sine, Triangle, Saw, Square and Pulse wave.
-   Set preset as wavetable: Sets a new wavetable on the active oscillator. This is created by a launching a background task with a copy of your preset and recording the audio.

### Pitch

-   RAT - Ratio:This is a multiplier on the frequency of the oscillator. Eg. if you are playing the note A4 (440hz) and the ratio is set to 2, this will multiply the pitch to 880Hz.
-   SEM - Semitone: Stepped pitch offset in semitones
-   FIN - Fine: Stepped pitch offset in cents
-   TUN - Tune: Smooth pitch offset in fractional semitones. Can be used to offset pitch at a higher resolution than cents eg. 0.0001 semitones (0.01 ct)

### Unison

-   VOC - Voices: Number of unison voices
-   DET - Detune: Controls the maximum offset in cents of the unison voices
-   SPR - Spread: Controls the bias of the panning towards the center or to the sides
-   WID - Width: Controls the maximum left/right panning

### Bottom controls

-   Phase: Offset applied the phase of the oscillator and all of its unison voices
-   Wave: Wavetable position.
-   Bend -/+, Asym -/+, Sync, Window
-   Harmonic filters:

    Ghost can manipulate the harmonics of wavetables directly. A useful way to think about harmonics is as range of sine waves with different amplitudes and phases. Tools like frequency spectrum analysers are great for displaying the harmonics produced by an oscillator, especially a saw oscillator. We will describe lower frequency harmonics as being 'to the left', and higher harmonics as being 'to the right'.

    -   None
    -   LP: Low pass filter than smoothly removes the wavetables harmonics starting from the right.
    -   HP: High pass filter than smoothly removes the wavetables harmonics starting from the left.
    -   Stretch: Moves the wavetables harmonics N places to the right and places each harmonic N spaces from one another, where N is a value controllable value from 0-19
    -   Shift: Moves the wavetables harmonics N places to the right as a group, where N is a value controllable value from 0-30.

-   Pan: Pans all unison voices by a given amount
-   Morph: When active, creates a smooth step between wavetable shapes. This may desirable for long and slowly evolving wavetables. When turned off, it creates a hard step from one wave shapes to another. This may be desirable for wavetables containing a variety of shapes different from one another.
-   Retrig: When active, causes the starting phase of each unison voice to begin at the value set by the Phase parameter. When inactive, the starting phase of unison voices will be randomised.
-   Dir Out: The output of this oscillator will bypass processing in the FX rack.

### Filter

Click on the circle or the title "Filter" next to it to activate/deactivate the filter. Additionally, double clicking the image of the filter will activate/deactivate the filter.

Clicking and draging the image of the filter will move the frequency and resonance parameters. Additionally, scrolling with a mouse wheel or touchpad will create the same effect.

You can toggle between the _frequency_ and _phase_ response of a filter by right clicking on the image.

This filter is polyphonic, meaning that each key press uses its own filter. For a non polyphonic filter, see the FX section.

-   Types - Use the arrow buttons to cycle through different modes, or click on the label to open a dropdown menu listing all types. Ghost contains many exciting filters for manipulating your sound. They are secret sauce and will not be explained! Try them yourself and have fun with them.
-   KTRK - Keytracking that moves the filter cutoff relative to the key that is pressed.
-   Freq - Frequency: Position of the filter in Hz
-   Res - Resonance: Increases/decreases the peaks of filters.
-   Morph - Additional control for changing the shape of filters. Only used by certain filter types
-   Mix - Wet/Dry control

### Distortion

Click on the circle or the title "Distortion" next to it to activate/deactivate the distortion. Additionally, double clicking the image of the distortion will activate/deactivate the distortion.

Clicking and vertically draging the image of the distortion will move the drive parameters. Additionally, scrolling with a mouse wheel or touchpad will create the same effect.

This distortion is polyphonic, meaning that each key press uses its own distortion. For a non polyphonic distortion, see the FX section.

-   Types - Use the arrow buttons to cycle through different modes, or click on the label to open a dropdown menu listing all types. Ghost contains many exciting distortions for manipulating your sound. They are secret sauce and will not be explained! Try them yourself and have fun with them.
-   Drive - Increase/Decrease the amount of distortion
-   Mix - Wet/Dry

## FM Matrix

Each of the letters in corresponds to an oscillator. You can left click them to switch the active oscillator. A double left click or a single right click will toggle them on/off.

Each letter is aligned diagonally to create a table of rows and columns, with the first row and column being F and the last column and second last row being A. The final row at the bottom is reserved for audio output.

The intersection between columns and rows contains a paramter controlling the FM amount for that oscillator.

For your conventience, the matrix contains a few different symbols that indicate different kinds of routing:

-   Triangle pointing downwards: FM feedback. These are located above each letter.
-   Triangle pointing right: Oscillator output volume.
-   5 point cross/start: FM amount from one oscillator into a seperate oscillator.

# Modulators

Most parameter values can be changed in real time by mapping them to modulators. Modulators offset the current position of any parameter by a range of up to -100% to 100%.

## E1-E6 Envelope

This is an extension on the classic ADSR controls found on many synths.

ENV1 is automatically linked to oscillators A-F.

-   Delay - Upon retriggering, holds a value of 0% for a given duration
-   Attack - Ramp from 0-100% for a given duration
-   Hold - Holds a value of 100% for a given duration
-   Decay - Ramp from 100% to the value set by the Sustain parameter for a given duration
-   Sustain - Holds a given value until for as long as a key or sustain pedal is held down.
-   Release - Ramp from the value set by the Sustain parameter to 0% for a given duration

-   Magnifying glass - Zoom +/-

### Grid

These parameters also can be controlled by clicking and dragging the points displayed on the grid.

Intersections between points on the grid can skew the ramp up/down. Double clicking

#### Menu

Open the menu by right clicking on empty space in the grid:

-   "Copy ENV to" - Copy parameter settings and parameter modulations to another ENV.

### L1-L6 - LFO

-   Save button - Save the LFO shape to a file.
-   Preset name - Opens a dropdown menu to browse different shape presets.
-   Retrig - When active, retriggers will reset the phase to 0%
-   Loop - When active, the phase of the LFO will start again from 0% after it hits 100%
-   Rate types

    Type of rate the "Rate" parameter should use

    -   Hz - LFO speed in Hz
    -   Beat Sync - Syncs the rate based on the BPM set by your DAW. If using the standalone version, the BPM defaults to 120.
    -   Keytracking - Maps the LFO rate to the rate of the last key being pressed eg A4 440Hz. The "Rate" parameter controls a semitone offset which can be used to increase or decrease the rate

-   Amount - Range from 0-100% that can be used to quickly and dynamically reduce the amount of modulation sent to other parameters.

### Grid

#### X / Y

Increase / decrease the number of horizontal / vertical segments in the grid

#### Points

Left click and drag to add points. Hold the Alt(Windown) or Option (macOS) key while dragging to snap the point to the grid.

Double left click on a empty space will add points. Double left click on points to remove them.

The intersection between two opints can be clicked dragged up and down to ramp up/down. Double clicking on the intersections between points will reset the ramp to a striaght line.

#### Menu

Open the menu by right clicking on empty space in the grid:

-   Reset points - Resets points to a the default triangle shape.
-   Random shape - Randomly places points based on the X/Y grid. Increasing the number of X or Y grid points will increase the complexity of the generated shapes and vice versa.
-   Random sequence - Randly places ramp and step shapes on the grid based on the X/Y grid. Increasing the number of X or Y grid points will increase the complexity of the generated shapes and vice versa.
-   Set shape on OSC (X) - Renders the LFO shape to a wavetable shape and replaces the wavetable used by the current oscillator
-   Add shape to OSC (X) - Renders the LFO shape to a wavetable shape and appends it to the current oscillators wavetable.
-   "Copy LFO to" - Copy parameter settings and parameter modulations to another LFO.

## F1-F6 - Frequency LFO

-   Save button - Save the FREQ shape to a file.
-   Preset name - Opens a dropdown menu to browse different shape presets.
-   Retrig - When active, retriggers will reset the phase to 0%
-   Loop - When active, the phase of the FREQ will start again from 0% after it hits 100%
-   Rate types

    Type of rate the "Rate" parameter should use

    -   ms - FREQ speed in ms
    -   Beat Sync - Syncs the rate based on the BPM set by your DAW. If using the standalone version, the BPM defaults to 120.
    -   Keytracking - Maps the FREQ rate to the rate of the last key being pressed eg A4 440Hz. The "Rate" parameter controls a semitone offset which can be used to increase or decrease the rate.

-   Transpose - Offset in semitones applied to the points in the grid.

#### Menu

Open the menu by right clicking on empty space in the grid:

-   Reset points - Resets points to a the default ramp down shape.
-   "Copy FREQ to" - Copy parameter settings and parameter modulations to another FREQ.

## R1-R3 - Random LFO

-   Retrig - When active, retriggers will generate new random values
-   S & H - Sample and hold - When active, creates hard steps from one random value to another. When inactive, creates a smooth ramp from one random value to another.
-   Stereo - When active, random values will be independantly generated for the left & right channel
-   Rate types

    Type of rate the "Rate" parameter should use

    -   Hz - LFO speed in Hz
    -   Beat Sync - Syncs the rate based on the BPM set by your DAW. If using the standalone version, the BPM defaults to 120.
    -   Keytracking - Maps the LFO rate to the rate of the last key being pressed eg A4 440Hz. The "Rate" parameter controls a semitone offset which can be used to increase or decrease the rate

-   Random - Controls the chance for new random values to be created at the interval set by the Rate parameter. With Random set to 0%, no new values will be produced and the RAND mod will freeze its state. With Random set to 100%, new values are always produced
-   Steps - Controls range of possible random values

## M1-M4 - Macros

Macros can be used to control multiple parameters using a rotary knob.

To modulate a parameter using a macro, simply left click and drag on the label "M1" or crosshair icon and drop it on the parameter of choice.

You can add your own custom label to macros by using a single left click on the label or crosshair icon.

## KEY - Keytracking

Keytracking will offset a paramters value relative to the MIDI key that is being pressed. MIDI keys have corresponding note numbers that range from 0-127, with Middle C usually being number 60 (~47%). These values can be remapped using the X/Y grid

## VEL - Velocity

Velocity will offset a paramters value relative to the velocity in which MIDI notes have been played. MIDI velocity ranges from 0-127. These values can be remapped using the X/Y grid

## AT - Aftertouch

Aftertouch will offset a paramters value relative to the MIDI aftertouch messages sent to the synth. These values can be remapped using the X/Y grid

> !Important
> There are two common types of aftertouch messages: "Channel" and "Polyphonic". Both kinds are read by the AT mod. In the rare case that your DAW and/or connected MIDI device is sending both types of aftertouch messages at once, you may get conflicting and undesirable results.

# Keyboard

-   Bend - Controls the maximum range -/+ in semitones of the pitch wheel
-   Pitch Wheel - Corresponds to the pitch wheel found on some MIDI keyboards. Can be dragged to transpose the pitch of all keys up and down.
-   PW - Pitch Wheel modulator. Offsets a parameters position based on the position of the Pitch Wheel.
-   Mod wheel - Corresponds to the mod wheel found on some MIDI keyboards. Can be mapped to control other parameters.
-   MW - Mod Wheel modulator. Offsets a parameters position based on the position of the Mod Wheel.
-   Keyboard - Displays keys that are currently held down. Click and drag the keys to play notes. The buttons to the left and right transpose the keyboard by an octave.
-   Polyphony - Limits the available voices to the range 1-16. Each key you press will consume an available voice. If there are no available voices, the voice will be stolen. If multiple keys are held down forming a chord, the voice stealing algorithm attempts to intelligently steal voices from the middle of the chord, making it easier to hear things like bassline progression and top melodies.
-   Legato - When active, voices that have been stolen will blend more smoothly into one another. This affects things like:
    -   Portamento: Blend duration from the pitch of the previous key to the new one. Blending follows a ramp which is controlled by the Curve parameter to the right.
    -   ENV: If a voice is stolen while legato is on and the key is not in a release state, the ENV will not retrigger. If the ENV is in a release state, the ENV will retrigger, causing it to start again from its Delay phase, but beginning from the last Y position (0-100%) it was in at the time of the retrigger. If Legato is inactive, the ENV will always retrigger, performing a hard reset, moving the ENV playhead back to the beginning with Delay producing Y values of 0%.

# Modulation Routing Table

Here you can add and remove modulations on parameters throughout the entire synth from one interface.

The drag handles on the left mean you can drag to reorder the rows.

## Columns

-   Row number: Double click on a row number to enable/disable the modulation of the selected parameter.
-   Modulation: Left click the table cell to open a drop down menu will list all available modulation sources. Choose an item from the menu to add/change/remove a modulation.
-   Parameter: Left click the table cell to open a drop down menu will list all available parameters. Choose an item from the menu to add/change/remove a modulation. This parameter can be automated too by simply dragging and dropping modulations onto them, or by chosing their name from the menu.

    Ghost has a lot of parameters, so for sake of keeping the list simpler, some parameters that are not in use by the current patch are hidden from the list eg. if the FX rack is empty, no parameters from effects will be in the list until new items are added.

-   Amount: Increases the range of modulation applied to the parameter
-   Skew: Pulls or pushes the modulation curve to the start or end of the range.
-   Polarity: Toggle between one-way or two way directions for your modulation. With one way, the range of modulation begins from the current position of parameter and ends to the left or right of parameter. With two-way, the range begins on one side of the paramter position and ends on the opposing side.

# FX

The area on the left is a list that can hold up to 6 of any FX type and in any order.

Simply left click and drag on the list items or reorder them.

The coloured bar on the left toggles the FX items "bypass" state.

If you right click on a list item you will open up a dropdown menu with the following options:

-   Bypass: Enable or disbale processing for this FX item.
-   Duplicate: Creates new copy of the FX item, copying the parameter values and modulations.
-   Delete: Removes the items from the list, additionally resetting any parameters and removing any connected parameter modulations.

## Chorus

An effect usually consisting of 1 or more short delays with modulating delay times.

The display up the top is an oscilloscope that visualises the audio input sent to the chorus. The oscilloscope shape is duplicated depending on the number of set voices and phase shifted depending on the chorus's delay settings.

GHOST intelligently calculates shape & position of the main oscilloscope shape by checking pitch & phase information from oscillator A on the last key you pressed.

The display down the bottom can be used to control filters to the wet signal. Left click and drag them to move their positions. Double click the icons to toggle the filters on/off.

Parameters:

-   Voices: Number of individual delays to use
-   Rate: Frequency of the internal LFO which moves the delay position
-   Delay: Delay offset from the dry signal
-   Depth: Changes the range the delays (or voices) in which the delay position is modulated
-   Feedback: Controls how much of the wet signal is sent back into the delay buffer along with the dry signal.
-   Low Cut: Controls the position of a high pass filter applied to the wet signal. This filter can be turned on/off by clicking on the label, or the corresponding icon in the bottom display to the right.
-   High Cut: Controls the position of a low pass filter applied to the wet signal. This filter can be turned on/off by clicking on the label, or the corresponding icon in the bottom display to the right.
-   Mix: Wet / dry

## Compressor

An effect that squashes audio with basic transient shaping controls.

The display to the left shows the peak amplitude of the dry signal, after the pre-gain has been applied and before compression is applied. The line starting from South-West and travelling North-East shows the waveshaping curve applied by the compressor. You can drag you mouse along the X:Y axis to control the threshold & ratio.

The display to the right is a moving graph that shows how much the audio was compressed.

Parameters:

-   Pre gain: Applies gain adjustment to the dry signal before entering the compression stage.
-   RMS: Toggles peak detection modes. With RMS on, attacks in transients tend to be a bit softer.
-   Knee: Applies a wider/narrower slope to the compression, anchored around the threshold. A wider knee tends to reduce saturation that results from compressing the audio.
-   Threshold: Sets the position where the compression is applied.
-   Ratio: Controls how hard to compress the audio when the amplitude surpasses the threshold
-   Attack: Applies a gradual delay to the compression when the signal exceeds the threshold.
-   Release: Controls how quickly the compressed signal returns to its normal level after falling below the threshold.
-   Post Gain: Applies gain to the wet signal after leaving the compression stage
-   Mix: Wet / dry

## Delay

-   Left: Delay time for the left channel
-   Right: Delay time for the right channel
-   Link: When active, sets the Right delay time to match the Left delay time. When inactive, both Left and Right can be moved independently
-   Feedback: Amount of delayed signal that is sent back into the delay buffer.
-   Sync: When active, sets the Left & Right delay time to beat values relative to the BPM set by your DAW. When inactive, the Left & Right delay time is in milliseconds.
-   P. Pong: When active, sends the left & right input signal into the left delay buffer with feedback sending the signal into the opposite channel. This produces an effect of the delayed sound 'bouncing' from the left and right speaker.
-   Low Cut: Controls the high pass filter cutoff applied to the dry signal before its sent to the delay buffer. Clicking the label with enable / disable the filter. You can also left click and drag the corresponding icon in the display at the bottom
-   High Cut: Controls the low pass filter cutoff applied to the dry signal before its sent to the delay buffer. Clicking the label with enable / disable the filter. You can also left click and drag the corresponding icon in the display at the bottom
-   Mix: Wet & Dry

## Distortion

-   Types +/-: Cycle between different distortion types
-   Drive +/-: Increases/decreases the distortion effect
-   Link: When active, makes the negative type and drive match the setting of the positive type & drive. When inactive, the negative type & drive can be changed independantly of the positive.
-   Mix: Wet & dry
-   DC Filter: Applies a high pass filter at 5Hz
-   Pre & Post Filter

    Clicking the label of the Pre & Post filter will toggle them on & off.

    -   Types: Cycle through different filter algorithms.
    -   Freq: Position of filter
    -   Res: Resonant peak of the filter
    -   Mix: Wet & dry

## EQ

Double click on empty space to add a band.

Double click on a band to toggle it on/off.

Bands can be dragged around the grid.

While dragging a band, you can holding the alt (Windows) or option (macOS) key and drag vertically to change the Q of the band.

While hovering over a band, you can use the wheel of a mouse or a two-finger scroll with a touchpad to change the Q of the band.

Clicking on a band will set the rows of controls below to correspond to that band. Notice the colours of the controls changing to match the clicked band.

-   Bypass: Turns the band on & off
-   Types: Choose between different EQ shapes
-   Freq: Frequency of the band.
-   Gain: Gain applied to the band. Only used by the peak and shelf EQ types.
-   Q: Controls how wide/narrow the effect of the EQ is.
-   Clear: Resets all values on the band to default and turns the band off.

## Filter

Clicking and draging the image of the filter will move the frequency and resonance parameters. Additionally, scrolling with a mouse wheel or touchpad will create the same effect.

You can toggle between the _frequency_ and _phase_ response of a filter by right clicking on the image.

-   Types - Use the arrow buttons to cycle through different modes, or click on the label to open a dropdown menu listing all types. Ghost contains many exciting filters for manipulating your sound. They are secret sauce and will not be explained! Try them yourself and have fun with them.
-   Freq - Frequency: Position of the filter in Hz
-   Res - Resonance: Increases/decreases the peaks of filters.
-   Morph - Additional control for changing the shape of filters. Only used by certain filter types
-   Pan - Applies a stereo offset to the position of the filter in the left channel, and the opposite offset to the filter position in the right channel.
-   Mix - Wet/Dry control

## Flanger

Clicking and draging the image of the flanger will move the frequency and feedback parameters. Additionally, scrolling with a mouse wheel or touchpad will create the same effect.

-   Types: Choose between flanger modes
    -   Top: Feedforward
    -   Mid: Feedback
    -   Bottom: Dual feedforward & feedback
-   Frequency - Position of the flanger in Hz
-   Feedback - Controls the strength of the signal sent into the delay buffer.
-   Rate - Frequency of the internal LFO which modulates the position of the flanger.
-   Depth - Controls the range of modulation applied to the position of the flanger by the LFO.
-   Stereo - Stereo offset for the internal LFOs phase
-   Mix - Wet/Dry control

## MB Compressor

Bands are split into three: low, mid and high. Each band of audio passes through a clipping stage before the compression stage.

The crossover between can be adjusted by dragging the vertical markers [show image]

The row of controls at the bottom correspond to the active band, and can be identified by their colour which matches the band. The active band can be changed by clicking anywhere within the band.

The rows of coloured horizontal lines indicate the ratio of updawards or downwards compression applied to the band. This can be dragged to increase or decrease the ratio. The final horizontal line the bands threshold, which can also be dragged.

The labels "In gain" and "Out gain" correspond to the pre & post gain of each band.

Clipper:

-   Pre Gain: Applies gain adjustment to the dry signal before clipping.
-   Clip: Threshold in which to apply clipping

-   Attack: Applies a gradual delay to the compression when the signal exceeds the threshold.
-   Release: Controls how quickly the compressed signal returns to its normal level after falling below the threshold.
-   Knee: Applies a wider/narrower slope to the compression, anchored around the threshold. A wider knee tends to reduce saturation that results from compressing the audio
-   Post gain: Applies gain to the wet signal after leaving the compression stage
-   RMS: Toggles peak detection modes. With RMS on, attacks in transients tend to be a bit softer.

## Phaser

Clicking and draging the image of the phaser will move the frequency and feedback parameters. Additionally, scrolling with a mouse wheel or touchpad will create the same effect.

-   Polarity: Toggles the polarity of the phasers feedback.
-   Poles: Morph between 4/8/12 pole phaser modes
-   Frequency: Position of the phaser in Hz
-   Feedback: Controls the strength of the feedback.
-   Spread: Expands or contracts the frequency response
-   Rate: Frequency of the internal LFO which modulates the position of the phaser
-   Depth: Controls the range of modulation applied to the position of the flanger by the LFO.
-   Stereo: Stereo offset for the internal LFOs phase
-   Mix: Wet/dry

## Reverb

-   Size: Controls the size of the simulated room.
-   Reflections: Controls how the signal is diffused. Lower settings create a shaper delayed slapback effect, higher settings smooth the delay.
-   Width: Controls the stereo width of the wet signal
-   Sidechain: Sidechains the wet signal using the dry signal
-   Decay: Controls how long the reverb rings for.
-   Low Cut: Controls the high pass filter cutoff applied to the wet signal. Clicking the label with enable / disable the filter. You can also left click and drag the corresponding icon in the display at the bottom
-   High Cut: Controls the low pass filter cutoff applied to the wet signal. Clicking the label with enable / disable the filter. You can also left click and drag the corresponding icon in the display at the bottom
-   Mix: Wet/dry
