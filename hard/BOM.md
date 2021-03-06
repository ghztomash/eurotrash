**/* BOM for eurotrash wav player */**



0805 resistors:

- 100R :         4x 
- 220R :         2x 
- 470R : 	 2x  
- 510R :         10x (these values are not critical, you could just get a bunch 220R or 470R and use them wherever it says 510R)
- 1k :           4x
- 10k :          4x
- 20k :          2x
- 22k :		 2x	
- 33k :		 6x	
- 100k :         12x

1206: 

- 10R : 1x (or use 1206 ferrit bead, rated 1A. or if you prefer 0805, that'll be ok, too)

0805 caps (16V or better):

- 20pf :          2x (NP0/C0G, ceramic) 
- 3n3  :          2x (NP0/C0G, may be 1206)
- 100n :         22x (ceramic)
- 300n :          2x (ceramic) 
- 1  uf:          2x (ceramic, may be 1206)
- 2.2uf:	  2x (ceramic, may be 1206)
- 10uf :          2x (ceramic, or tantal)	  

caps (electrolytic), through hole (25V or better):

- 10uf : 	  1x
- 22uf :	  4x

		
ICs/semis:

- BAT54s (schottky diode, sot-23) : 4x (mouser # 78-BAT54S-G3-08)
- MMBT3904 (NPN trans., sot-23) : 2x (mouser # 512-MMBT3904)
- SM5817 diodes : 2x (mouser # 833-SM5817PL-TP)
- **TL072** (SOIC) : 2x (*)
- TL074 (SOIC) : 1x
- PCM5102a (TSSOP) : 1x (mouser # 595-PCM5102APWR)


voltage regulators/references:

- ADP150 (3v3 regulator, TSOT): 1x (mouser # 584-ADP150AUJZ-3.3R7)
- LM1117-33 (3v3 LDO reg., SOT-223): 1x (mouser # 511-LD1117S33)
- LM1117-50 (5v0 LDO reg., SOT-223): 1x (mouser # 511-LD1117S50)

- REV0: **79L05** -5v (TO-92): 1x (**better choice would be: LM4040-5** + 500R (0805)) (****) (mouser # 926-LM4040DIZ50NOPB)
- REV1: LM4040-5 (TO-92): 1x
- REV1: LM4040-3 (sot-23): 1x (NB this is optional: can be used for AREF; not really needed for the wav player)

misc:

- inductor 10uH (SMD/1206): 1x (mouser # 81-LQH31MN100J03L)
- 16MHz crystal (HC/49us): 1x (mouser # 59-FOXS160-20-LF)
- atmega328p : 1x (TQFP)  (mouser # 556-ATMEGA328P-AU)
- teensy3.1  : 1x (**don't forget to cut the usb/power trace**) (http://store.oshpark.com/products/teensy-3-1)
- 2x single row precision ("machined" / "round") pin header and sockets for teensy 3.1 (only the outer pins are used, so we need 14 pin, RM2.54)
- 2x3 RM2.54 pin header (ISP)
- 2x5 RM2.54 pin header (eurorack power connector)
- molex micro SD card socket (# 502774-0891, mouser # 538-502774-0891)
- **winbond W25Q128FV** (SPI flash) (**)
- jacks: 10 kobiconn / thonkiconn
- rotary encoder w/ switch: 2x (for instance: mouser # 652-PEC11R-4215F-S24 (15 mm, 'D' shaft); 652-PEC11R-4215K-S24 (15 mm shaft,      knurled); 652-PEC11R-4220F-S24 (20 mm, 'D'), 652-PEC11R-4220K-S24 (20 mm, knurled), etc)
- knobs (to match): 2x (ideally, with small(ish) diameter (12mm or so max) and no indication line. Cliff K88, for instance, are fairly nice/suitable)
- 128x32 SPI oled: adafruit ( https://www.adafruit.com/products/661#Technical_Details ) 
- **8 pin header for oled** + 8 pin socket (low profile), RM2.54 (***)

notes: 

(*) something fancier can be used for the audio output, of course (one of the dual op amps is for audio out, 
the other is used for the digital outputs). 
i've tried both _OPA1662 and AD8599_ in the audio path - not sure whether i'd notice the difference, YMMV.
     
(**) the spi flash is optional; it's a very nice add-on though, as it allows for lower-latency one-shot triggering compared to streaming from SD card (~4ms vs ~8ms). the winbond ICs are a bit hard to find, i got mine from alibaba. when using it, you'll also need 3x 100R more (0805) (in the unlikely event you got these in multiples of 1)). (there's pin/software compatible alternative ICs at mouser and the usual places, which should work, but they're not confirmed working atm); 

(***) you can solder the oled directly to the board (with the pin header) — which evidently isn't ideal; one way around this is to put the *socket* onto the oled and use headers like these http://www.taydaelectronics.com/stackable-header-8-pins-2-54mm.html ,  pushing them from up from the bottom of the board. for the socket, something like BKL Electronic 10120828 will be suitable. also see build doc. 

(****) using a 79L05 is entirely ok, but using a LM4040-5 will result in somewhat better ADC performance. (see build instructions). 

