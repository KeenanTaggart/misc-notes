Stunt Race FX Frame Rate on Original SNES Hardware
Typical Frame Rate During Gameplay
On original Super Nintendo hardware (with the Super FX chip in the cartridge), Stunt Race FX runs at a very low frame rate by modern standards. In regular races with multiple competitors, the game often only manages around 10–15 frames per second (FPS)​
gamefaqs.gamespot.com
. Players at the time noticed the choppy performance – one even described it as “low detail polygons in a tiny scaled-down window, going at like 10 FPS”​
gamefaqs.gamespot.com
. In fact, the developers letterboxed the gameplay view (shrinking the 3D view’s size on screen) specifically to reduce the rendering load, yet the frame rate still struggled to stay in double digits​
gamefaqs.gamespot.com
. By comparison, standard SNES games (without the Super FX) typically ran at 60 FPS (or 50 FPS on PAL consoles) and only occasionally dipped lower​
forums.nesdev.org
 – Stunt Race FX’s 3D engine was an outlier, running at a fraction of that speed due to its heavy demands. Notably, Stunt Race FX’s frame rate varies depending on the game mode and scene complexity. For example, the Time Trial mode (where you race alone on the track) runs considerably faster than the standard racing mode with rivals on-screen​
highwayforever.wordpress.com
. With no other vehicles to render, the Super FX chip can push a few more frames per second – the increase in smoothness is immediately noticeable when switching from Time Trial back to a normal race​
highwayforever.wordpress.com
. This suggests that the average frame rate under lighter loads was closer to the upper end of the game’s capabilities (approaching the mid-teens FPS). Indeed, the Super FX-powered engine appears to top out at roughly 20 FPS under ideal conditions on NTSC hardware​
forums.nesdev.org
. (Analysts note that ~20 FPS was effectively the ceiling for games like Star Fox and Stunt Race FX on SNES, and even that is rarely achieved in practice​
forums.nesdev.org
.) The PAL version of the game could theoretically reach ~25 FPS (since the PAL SNES runs at 50Hz) if the hardware allowed it, but in practice the PAL version also suffered from the same slowdowns and low averages as the NTSC version (just with a slightly different upper limit).
Frame Rate Drops in Heavy Scenes
While ~10–15 FPS is typical for Stunt Race FX, certain situations cause the frame rate to drop even further. Complex or object-heavy scenes (for instance, tracks with lots of polygonal scenery, multiple cars, or special effects) can push the FPS into the single digits. Players have reported that in the most extreme cases the game can dip to as low as ~5–6 FPS​
resetera.com
, turning the race into a veritable slideshow. One anecdote claims Stunt Race FX “gets a solid 6 FPS some of the time” during busy moments​
resetera.com
. A particularly notorious example is the “Aqua Tunnel” track, which fans identified as having one of the worst slowdowns in the game – the frame rate on this water-themed track is especially bad, noticeably more choppy than other courses​
justgamesretro.com
. In general, whenever “a million billion objects” (as one retro review jokingly put it) are on screen at once, the Super FX chip simply can’t keep up​
justgamesretro.com
. The result is severe choppiness and stutter in the visuals and even a laggy feel to the controls. (At such low frame rates, input latency increases – e.g. players observed a slight delay between pressing a button and seeing the response, especially when the screen was busy​
justgamesretro.com
​
gamefaqs.gamespot.com
.) To mitigate these slowdowns, some enthusiasts have resorted to hardware modifications or emulation tweaks. There are reports of people overclocking the Super FX chip by swapping out the cartridge’s oscillator to run it at a higher frequency, which can boost the frame rate a bit​
gamefaqs.gamespot.com
. One such modder noted that increasing the Super FX clock yielded only a small FPS gain (on the order of a few frames per second), but when your baseline is around 10 FPS, even a jump to ~13 FPS is very noticeable​
gamefaqs.gamespot.com
. In other words, Stunt Race FX’s baseline performance is so low that a difference of just 2–3 FPS can be significant​
gamefaqs.gamespot.com
. This speaks to how severe the frame rate limitations are on the original hardware.
Super FX Chip Performance Limitations
The poor frame rate of Stunt Race FX can be directly attributed to the limitations of the Super FX graphics co-processor and the SNES hardware environment it operates in. The Super FX is a custom 16-bit RISC chip that acts as a graphics accelerator, designed to compute 3D polygons and draw them into a frame buffer​
en.wikipedia.org
. While revolutionary for bringing polygonal 3D to the SNES, the Super FX chip in Stunt Race FX is still very modest in horsepower – it runs at approximately 10.5 MHz (original Super FX) up to 21 MHz (in later revisions/high-speed mode) and can execute only a limited number of operations per frame. This means there is a hard cap on how much 3D rendering can be done in one 1/60th of a second. In practice, Stunt Race FX cannot remotely approach 60 FPS; instead, it struggles to complete its calculations in time for even 15–20 FPS output. In fact, the game logic/engine itself appears to be capped around 20 FPS (with each frame of gameplay often spanning 3 or more video refreshes)​
forums.nesdev.org
​
forums.nesdev.org
. Even if the Super FX had occasional headroom, the SNES would still only present new frames at these subdivided intervals. Several technical factors explain why the frame rate hovers so low:
8bpp Frame Buffer (High Color Mode): Stunt Race FX renders its 3D graphics in 8-bit per pixel color, meaning it can display up to 256 colors for richer visuals. However, using an 8bpp frame buffer doubles the amount of data that must be drawn and transferred each frame compared to a 4bpp (16-color) buffer. This decision “probably murdered the frame rate”​
forums.nesdev.org
. Developers on the nesdev forums note that both Doom and Stunt Race FX (which use 8bpp) take roughly twice as long to fill and clear the screen as games like Star Fox that used 4bpp, drastically reducing the peak attainable FPS​
forums.nesdev.org
. In other words, Stunt Race FX chose better color depth at the cost of speed. The Super FX chip has to plot every pixel of the 3D scene, and more bits per pixel means more work. The theoretical maximum frame rate with an 8bpp buffer was calculated to be around 20 FPS, and even that assumes optimal conditions​
forums.nesdev.org
.
Limited Fill Rate and Polygon Throughput: The Super FX chip’s fill rate (pixel-drawing speed) is the primary bottleneck in Stunt Race FX. Even at 21 MHz, the chip can only draw so many pixels per frame. For example, one analysis showed that simply clearing the screen and drawing a full frame at low resolution could consume over half of the Super FX’s available cycles per frame​
forums.nesdev.org
​
forums.nesdev.org
. Complex scenes with many polygons will easily exceed these limits, requiring multiple frame ticks to complete. The more polygons and the larger they are on screen, the longer the drawing takes​
forums.nesdev.org
​
forums.nesdev.org
. This is why the game slows down when objects get close to the camera or when several racers are in view – the chip is trying to draw more (and bigger) triangles, and it simply can’t maintain the same speed​
forums.nesdev.org
. There’s a trade-off between detail and frame rate: Stunt Race FX pushed a higher detail level (more colors, moderately complex car models, etc.) which inherently limits FPS on the Super FX. By contrast, Star Fox kept polygon counts and colors simpler, which is partly why it runs slightly faster than Stunt Race FX (though still in the teens of FPS).
Small Output Window & DMA Bandwidth: To cope with the limited throughput, Stunt Race FX uses a small output window (the gameplay view is a reduced-size viewport within the screen). This decreases the number of pixels to draw. Even so, the SNES’s DMA bandwidth and cartridge RAM were finite. Each frame the Super FX must DMA copy the completed frame buffer to the SNES’s video memory for display​
en.wikipedia.org
. The developers wisely kept the resolution low enough that this transfer could fit within vblank periods. According to analysis, the bandwidth was “more than enough” for ~20 FPS at the chosen resolution​
forums.nesdev.org
, so the bottleneck was not so much the data transfer but the Super FX’s ability to do the drawing work in time. The SNES’s main CPU isn’t the issue either (it mostly stays idle or handles minimal logic while the Super FX does the heavy lifting). Essentially, the Super FX chip’s own processing limit is the key factor – its power was “reasonably well matched to the capabilities of the console”​
forums.nesdev.org
, meaning the chip could only generate content up to a certain speed that coincided with these low frame rates.
In summary, Stunt Race FX typically runs around 10–15 FPS on real SNES hardware, sometimes peaking closer to ~20 FPS in low-complexity moments and often dropping below 10 FPS in busy scenes​
gamefaqs.gamespot.com
​
forums.nesdev.org
. The Super FX’s limited 3D processing power, especially when using an 8bpp framebuffer and rendering a lot of polygons, is the root cause of these low frame rates​
forums.nesdev.org
​
forums.nesdev.org
. Players in 1994 did notice the choppiness – it’s frequently cited as the game’s biggest weakness – but it was the price paid to achieve 3D on the SNES. Only with hardware mods or emulator enhancements (like overclocking or fan-made patches) can Stunt Race FX run at significantly higher frame rates, since on stock hardware it is bound by the Super FX chip’s 3D performance limits. Despite the low FPS, many players still have fond memories of the game’s quirky fun – but there’s no denying that on original hardware, Stunt Race FX runs at a sluggish frame rate, with frequent drops, due to the technical constraints of the Super FX graphics chip​
gamefaqs.gamespot.com
​
forums.nesdev.org
. Sources:
Retro player impressions and forum discussions of Stunt Race FX’s frame rate​
gamefaqs.gamespot.com
​
gamefaqs.gamespot.com
​
resetera.com
Highway Forever blog – remarks on low frame rate (time trial vs race mode)​
highwayforever.wordpress.com
Technical commentary from SNES developers (nesdev forums) on Super FX performance and frame rates​
forums.nesdev.org
​
forums.nesdev.org
Just Games Retro review comments – noting worst slowdowns on certain tracks​
justgamesretro.com
 and control lag at low FPS​
justgamesretro.com
.
