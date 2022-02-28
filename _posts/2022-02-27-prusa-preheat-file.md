---
title:  "Prusa Preheat"
layout: post
---

### Using a GCODE file to preheat

Here's an easy way to set preheat temperatures on a Prusa.

Keep a file that sets your desired preheat temps on the SD card, and "print" it from the Prusa menu.  For example:

#### PETG preheat 170 & 75C.gcode
````
M104 S170 ; set nozzle temp to 170C, and continue without waiting
M140 S75 ; set bed temp to 75C, and continue without waiting
M84 ; disable motors to prevent popup showing that file is incomplete
M73 P100 R0 ; set print progress to 100% and time remaining to 0
````

170 and 75C work well with my i3 MK3.  The nozzle won't drool much, and when the print is launched both bed and nozzle will reach the final temps at about the same time.


Of course, preheat temps can be set directly through the Prusa menu, but I find it easier and faster to print a file from the SD card instead.



### Other files using the same idea
 
#### Nozzle heat 230C.gcode (for nozzle cleaning or filament changes)
````
M104 S230 ; set nozzle temp to 230C, and continue without waiting
M140 S0 ; set bed temp off, and continue without waiting
M84 ; disable motors to prevent popup showing that file is incomplete
M73 P100 R0 ; set print progress to 100% and time remaining to 0
````

#### temps off.gcode (to turn the heaters off)
````
M104 S0 ; set nozzle temp off, and continue without waiting
M140 S0 ; set bed temp off, and continue without waiting
M84 ; disable motors to prevent popup showing that file is incomplete
M73 P100 R0 ; set print progress to 100% and time remaining to 0
````



## Heading Two (h2)

### Heading Three (h3)

#### Heading Four (h4)

##### Heading Five (h5)

###### Heading Six (h6)
