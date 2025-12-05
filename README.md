# html-pngtuber
Yet another basic pngtuber

Damn basic and (per my understanding) easy-to-use pngtuber program.

This is a tool targeted for desktop use, so it won't be mobile-friendly.

## To use, just:
1. Open the page
2. "Start Microphone" (allow access to your microphone)
3. Load Idle/Speaking PNG files
4. Talk.

## Available adjustments inclide:
1. Audio volume multiplier
   > If your input volume is too low, increase this to make volume changes easier to identify.
3. Volume threshold
   > When to kick-in the "speaking" state.
5. Idle delay
   > How long should it wait before going back to "idle" state when volume is lower then the threshold.
6. Background color
   > Green screen, chroma key, ... etc. The color that should be filtered out and become transparent.
8. Avatar sets
   > Quickly switch up to 5 avatar sets.

## Tested with:
- OS: Windows 10
- Browser: Firefox Developer Edition
  * Normal browsers would do, but will stop updating the page if the window isn't visible. (aka, updates paused when not in foreground).
  * Easiest way to make it still work is just install Firefox Developer Edition and run it. Works unless minimized manually.
- Streaming Software: OBS

## Using with OBS (added on 20251205)
1. You can now add a browser source in OBS to better integrate the screen with your video stream!
2. Just open the main page (index.html) as usual and click on the "OBS Companion" button on the bottom, then copy the provided URL into OBS browser scene.

## Setup example for first-timers
> This is a setup example. You can follow the following instructions, but not necessarily need to be exactly the same.
1. Install [Firefox Developer Edition](https://www.firefox.com/channel/desktop/developer/)
2. Install [Open Broadcaster Software](https://obsproject.com/)
3. Open this tool, either:
   1. Download the file `index.html` and open it with Firefox Developer Edition, OR
   2. Open the ready-to-use version at https://htmlpngtuber.collies.dev/ with Firefox Developer Edition.
4. On the tool page:
   1. Click `Enable Microphone` and select the desired input device.
   2. Adjust volume threshold by toggling options:
      - Volume Threshold
        > - Try talking in your normal voice level and observe the volume % showed on screen. You can then adjust the threshold to match the correct voice level.<br>
        > - You want it to change to "Speaking" status once you start talking, and go back to "Idle" when you don't talk for awhile.
      - Volume Visualization Multiplier
        > If your voice level is too low to be seen clearly on-screen, try increasing the multiplier.
   3. Load files:
      - Idle PNG
      - Speaking PNG
   4. Set background color to `#FF00FF`
      > We'll use this value as the chroma key in OBS later.
5. Open OBS, then
   > It is okay for the Firefox window to be in the background (aka, covered by other windows), but DO NOT MINIMIZE the Firefox window.
   1. Add new scene
   2. Add new source
      - Type = Window Capture
      - Window = The Firefox instance that has this tool page opened.
   3. Right click on the source → Transform → Edit Transform → Adjust crop value so only the pink (magenta) region is selected.
   4. Right click on the source → Filters → Add Effect Filter
      - Type = Chroma Key
      - Key Color Type = Magenta
      - Adjust options like `Similarity` and `Smoothness`
   5. Move the image to the bottom-right color.
   6. Add other sources like Games or Web pages.
   7. Start streaming!
      > Again, DO NOT MINIMIZE the Firefox window. Having it covered by other windows is okay.
