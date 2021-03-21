## Output frame locking
This technique allows to have output frame rate equaling to original emulated retro system. It gives a smooth scrolling and overall great experience in game playing.

## Analog TV
* All retro systems are targeted for analogue TV output which is very tolerant to off-spec parameters. Many PAL TVs can happily display frame rates as low as 47Hz or even lower. And it's the same for higher frame rates.
* Analogue TV doesn't have the parameter "pixel clock" as video is produced by continuous signal without quantization. So retro computers/consoles were free to choose any pixel clock most convenient for specific implementation. As a result, picture form such system had non-square pixel. And even if pixel looked like square it might be not 100% square as eye cannot distinguish small deviation on non-quantized analog display.
* Although analogue TV has defined amount of lines per field/frame it wasn't strictly followed by home systems. Some systems might supply 311 lines or 313 lines per field for PAL instead of standard 312.5. Some systems even supplied 320 lines due to simplified output logic giving in result 48Hz of frame rate.
* Some systems went more far and output irregular line lengths where some lines might be longer than others.

## Digital TV
Digital video output (such as DVI, HDMI, DP) consist on strict parameters where pixel clock, pixels per line and lines per frame are defined and cannot be changed (actually there are more parameters are strictly defined). Because digital cicquits are based on counter it cannot freely accept any changes from standard as it requires a special handling and more expensive chips, so in most cases any out of spec parameter making modern TV refuse to display and go to "no sync" or "no signal" state.

## The Problem
As you already guess it's a hard task to make retro system with usual deviation from standard to be displayed on modern digital TV. The most hard thing to manage is frame rate matching. Modern TV cannot output frame rates if it's not standard 60FPS or 50FPS. And retro system cannot change its frame rate as well!
Scalers usually deal with such frame rate difference using different kind of techniques and requires a lot of computing power for good results. Some TVs when get video from analogue source may change their screen frame rate according to source making the task more simple. Need to note here: the same TV usually don't accept the same non-standard frame rate from digital source as internal processing goes through different routes. Digital input carry not only video but other streams like audio and servicing info - so other parts of TV are included in the processing chain unlike the analogue input carrying just video.

## HDMI Output from MiSTer
MiSTer's main output is HDMI. As you know from above, even if modern TV can accept some deviation on analog input it's not the case of MiSTer providing the digital output. So, strict HDMI requirement is applied here. 
So, the task of frame rate conversion or matching lays on MiSTer. Being in the middle between emulated retro system and TV, the MiSTer cannot ask TV for specific frame rate output. In general case MiSTer also cannot ask for specific frame rate from emulated system as well. Emulated system has many parameters related to each other making impossible to change the frame rate. In theory it's possible to change the master clock of emulated system to some amount to let the output frame rate match the standard. In practice such relation to master clock is not so direct. Some systems may even supply different resolutions. And even if correct ratio between master clock and frame rate can be determined, the ratio itself may have long polynomial value like PI (3.1415926535..) So it won't be possible to set the clock without drifting the output frame start to either direction and eventually look like screen tearing.

## How it's done in some modern FPGA emulators
In case of single emulated system and if it's originally not so far from Digital TV standard like NES or SNES, it's possible to find some workaround by changing the master clock and adding some clock skip at some specific points. System will work a little faster or slower than original. User won't notice the change and system will have smooth scroll on HDMI.

## Why it's not implemented in MiSTer
Because MiSTer is multi-core system it will take enormously long time to tweak EVERY core. Cores have different complexity and tricks from one core aren't applicable to others. Cores may loose some compatibility with such tweaks. Original authors of many cores either abandoned it log time ago or have no interest to tweak it. Some cores output multiple resolutions so will require very complex tweaks (if ever possible). Overall the amount of work is much larger than for system with single core. Since MiSTer is open source - you can try your self in such tweaks.

**One more note:** MiSTer doesn't limit possible HDMI resolutions, so it will be additionally hard to tweak the core to match to any possible HDMI resolutions as timings of frame may not be exactly 60FPS or 50FPS.

## What MiSTer provides to solve the problem?
Since MiSTer has to deal with many different cores, some generic solution is required so it won't be intrusive into core's internal code.

And such solution has been found!

I found that some (not all!) TVs and Monitors can accept arbitrary pixel clock. For example FullHD pixel clock is 148.5MHz, but many TVs/Monitor may accept some range of clocks. Thus picture parameters are remained the same so digital parts of TV/Monitor will get their standard amount of pixels and lines, but they will work on slightly different frequency. MiSTer measure the frame rate of emulated system and re-calculates the pixel clock on HDMI output. As a result the output frame rate will match to input one with high precision. There still can be one frame repeat or drop but it will happen once per couple hours which is acceptable.

To enable this trick, you need to include **vsync_adjust=1** option to [MiSTer.ini](https://github.com/MiSTer-devel/Main_MiSTer/blob/master/MiSTer.ini) file and place this file into root of SD card.

So, if you are lucky to have such TV or Monitor then you can enjoy the smooth scroll as an universal solution for any core.
