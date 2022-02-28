---
title:  "Prusa Preheat"
layout: post
---

## Using a preheat GCODE file

Here's an easy way to set preheat temperatures on a Prusa.

Place a file on the SD card to "print" from the Prusa menu, which sets the desired temps.  For example:

### PETG preheat 170 & 75C.gcode
````
M104 S170 ; set nozzle temp to 170C, and don't wait
M140 S75 ; set bed temp to 75C, and don't wait
M84 ; disable motors to prevent popup showing that file is incomplete
M73 P100 R0 ; set print progress to 100% and time remaining to 0
````

170 and 75C are pretty good temps for my i3 MK3.  The nozzle won't drool much, and when the print is launched both bed and nozzle will reach the final temps at about the same time.


Of course, preheat temps could be set directly through the Prusa menu, but I find it easier and faster to "print" a file from the SD card instead.



## Other files using the same idea
 
#### Nozzle heat 230C.gcode (for nozzle cleaning or filament changes)
````
M104 S230 ; set nozzle temp to 230C, and don't wait
M140 S0 ; set bed temp off, and don't wait
M84 ; disable motors to prevent popup showing that file is incomplete
M73 P100 R0 ; set print progress to 100% and time remaining to 0
````

#### temps off.gcode (to turn the heaters off)
````
M104 S0 ; set nozzle temp off, and don't wait
M140 S0 ; set bed temp off, and don't wait
M84 ; disable motors to prevent popup showing that file is incomplete
M73 P100 R0 ; set print progress to 100% and time remaining to 0
````



## Heading Two (h2)

### Heading Three (h3)

#### Heading Four (h4)

##### Heading Five (h5)

###### Heading Six (h6)