HDMI output for NeoGeo AES
==========================

Standing on the shoulders of genius. I've not used github much and it feels a little wrong taking someone elses work and turning it into something that's your own. Anyway I've just found this amazing work by Charcole but find it strange that nobody has helped move this project forward for over 6 years so far. There are no other HDMI solutions for the NeoGeo that I can find online which take the data directly and give such low latency.

This has to tried on an AES system so I've stolen the correct schematic for the AES system from wiki.neogeodev.org and cleaned it up a bit in Photoshop and set about trying to work out the wiring for the home version.

I've then found and stolen a nice photo of an AES motherboard which beautifully shows how the chips are easily located using the letters down the left and the number across the top. These machines are so nicely designed :)

Anyway, someone (and I hope they are correct) helpfully penned in on the original schematic which LS273 is which and I've done the wiring table for the AES machine based from that. My new table has been added onto the bottom of the original wiring documment.

Once I have this working I'll update this with results however since whatching the second video on youtube from Charcole where he modifies an MVS-1 slot with the Yamaha sound chip it seems we will be missing a few analogue sound effects?

Original readme bellow;

---------------------------------------------------------------

HDMI output for NeoGeo MVS
==========================


Summary: The digital video and audio outputs from the Neo Geo MVS are tapped off before going through the DACs. Instead an FPGA reads the data and outputs the signal over HDMI forming a direct digital to digital connection.

This video should explain things:

<a href="http://www.youtube.com/watch?feature=player_embedded&v=bTamCo2C6kg
" target="_blank"><img src="http://img.youtube.com/vi/bTamCo2C6kg/0.jpg" 
alt="IMAGE ALT TEXT HERE" width="640" height="480" border="10" /></a>

The FPGA generates the HDMI video signal with data islands to embed the audio. It also controls the clock of the Neo Geo MVS so it can produce the exact 720x480p at 60fps timing that the HDMI specification demands. See the [notes](Notes.md) for more details.

If you've built hardware based on older releases of the [wiring](Wiring.md) information then note that in the new build I've changed pin 73 to pin 104 for the lowest bit of the blue channel. This is because pin 73 was connected to the power rail on the dev board.

*This project might also be notable in that it's one of the very few (that I know of) that features working audio over HDMI.*

*Nb. The code was originally based off the HDMI/DVI sample code from [fpga4fun.com](http://www.fpga4fun.com/HDMI.html).*
