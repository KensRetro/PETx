# This project is currently partially complete, please read the following carefully and make an informed decision before you attempt to build it.

I like to provide schematics in Eagle (version 7) because that's what I have used for years at work and it's easy to upgrade the files to 
newer versions or Kicad etc.  It's just a comfort thing for me, but if you change to another format please be sure to carefully check 
that everything looks as it should - conversions don't always go cleanly.  

DISCLAIMER: All information is provided 'AS-IS", I have tried to be as accurate as possible but that doesn't mean there are no mistakes. 
Any errors or omissions etc. are your own responsibility.  

# Project Notes : C64 sized PET - PETx

The prototype is based on the the 9 inch screen version of the PET (board #320349) so no CRTC chip is needed.
I added the video circuit similar to the ones posted around the net
It was also decided to go with a more similar to original re-creation as it makes it easier to substitute parts etc. 
and compatibility remains quite good.

# Changes / Updates in this version (PROTOTYPE): 
1. Added connections for RESET (momentary switch)
2. Added NO_ROM line for diagnostics
3. Added peizo buzzer for standard PET sounds
4. Added Video output circuit - HORIZ/VERT/VIDEO signals no longer attached to USER PORT (I left connection points but will need a
   jumper to connect if needed. This was done in order to facilitate routing, these lines to the user port are normally used for a
   video output circuit, since it's already on-board, it's not likely needed)
5. Added GRAPHIC signal to USER PORT (similar to 12" screen versions)
6. Removed memory expansion connections, definitely won't fit on the board and no known expansion units will fit in the case anyway
7. Changed Video RAM to a single 6116 chip instead of 2 x 2114 (availability)
8. Change ROM set to a single chip, added necessary decoding logic so I/O chip memory is not replaced.
9. Added a jumper to allow multiple ROM sets built in (could be connected to a switch)
10. Changed RAM to a single chip of 32K, this also allowed removal of +12V and -5V supplies and associated components saving a lot of space.
11. Removed CASSETTE #2 as it is rarely used, connection points are still available but no driver for the tape motor was included.
    Connection would have to be wired off the board if needed.
12. Added a couple sets of connection points for +5V and GND for add-ons (normally CASSETTE #1/2 was used for this)
13. Added optional 2nd RAM chip mapped into 9000-FFFF range, jumper (or switch configurable) for only being active over 9000-AFFF or 9000-FFFF for soft ROM option
14. Added option for 2nd RAM (9000-FFFF) to be "READ ONLY" or "READ WRITE"
15. Terminated unused gates to minimize potential noise.
16. Changed ROM socket to allow use of SST39SF010A as well as 27256 (4 ROM sets, Flash ROM, externally programmable)
17. Changed Character ROM to allow more fonts and use of SST39SF010A as well as 27xxx series Eproms.
18. Added power switch & connector that should fit into the existing C64 bracket  (if used)
19. Added access to unused RAM in 8000 area (8400-8FFF)
    
# Potential upgrades not currently incorporated:
(Feel free to suggest others)
1. Add a writable latch that controls some of the dipswitch selectable features above
    
# More Notes:
This project is a PET 2001, 9 inch screen version (started with schematic 320349). This model was chosen for 2 reasons, 
first, a CRTC chip is not required and second, it outputs a near standard video signal with the included interface.
The Intent was to make it fit into a C64 / VIC-20 case.
In order to Achieve this a reduced footprint was needed, so the changes above were implemented.
The parallel and Cassette #1 ports were designed to line up in the same place as the C64/VIC20 version.
The video output appears where the RF output jack was on the C64. This area is in the cartridge slot on the VIC20
The IEEE port appears where the C64 cartridge port was and covers the left 2/3 of the VIC 20 cartridge area.
The placements mean that no/few modifications are needed to the case of the C64 or VIC 20 to fit the board in.
Unfortunately, the power switch and joystick area ends up wide open, with the power switch and power cord coming out in that area.
Perhaps a 3D printed cover could be fashioned as a replacement.
Many other possible upgrades were considered but due to a lack of space and complexity, were rejected (for the prototype run at least).
Perhaps other additions or changes could be incorporated in a future version.
This project depends on the Commodore original prints being correct, some minor corrections were caught, but they were used as a base to start.
The Chip ID's on the silkscreen are those from the original PET layout and start with Uxxx, Chips that start with ICxx are additions or changes 
that have been incorporated to slim the footprint or facilitate routing.
Various keyboard options were considered but again, for the prototype at least, were sticking with a standard C64/VIC20 keyboard and a patched 
version of the edit ROM (or some other available hardware solution)

# BEFORE YOU BUILD:
Some of the parts are near impossible to find, specifically 3446 chips, 74177 chips, and 74154 chips in a DIP package. 
I have a replacement sub-board for the 3446 chips in another repository that has been tested successfully.
You can use 74197 chips as a direct replacement for the 74177, but they are very rare as well.
You can use a newer version of the 74154 chip but it seems to only be available in a SMT version, therefore an adaptor board may need to be created.

# PROTOTYPE VERSION:
This version has been created and tested.  Some small errors were corrected with bodge wires and an added chip and and it seems to function well and passes the diagnostic 
cartridge tests consistantly.

# RELEASE VERSION:
This version HAS NOT been created or tested (I didn't really need another hanging around)
The errors have been corrected in the schematic and board files and Gerbers have been created.

Changes to this version (REV.1) also include the following:
1) Added solder jumpers to allow WD6502 to be used
2) Changed Power supply to 1 regulator
   
TO DO:
1. check/fix alignment of mounting holes to C64 case (Not checked or tested in VIC20 case at this time)
