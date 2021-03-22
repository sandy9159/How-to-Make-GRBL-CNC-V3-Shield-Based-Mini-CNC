# How-to-Make-GRBL-CNC-V3-Shield-Based-Mini-CNC
This CNC is based on GRBL0.9 Firmware and CNC V3 shield GRBL is Hacked for Z-axis Servo.


Step 1

This CNC is based on GRBL0.9 Firmware and CNC V3 shield GRBL is Hacked for Z-axis Servo.

CNC Shield & GRBL combinly works very preciselyIt is loaded with very useful functions like Hard limit, Soft limit, Homing, etc

This is about how to make

GRBL+CNCV3 shield+Arduino based CNC machine

This guide include all necessary instruction required

like How to assemble CNC machine

How to Load GRBL to arduino

Inkscape extension installation

GRBL Configuration & G-code streaming

It is loaded with very useful functions like Hard limit, Soft limit, Homing, i will guide you in detail how to Make GRBL Based mini CNC machine at home


Before we proceed further I would like to tell you about https://jlcpcb.com/IAT

JLCPCB are the leader in PCBC manufacturing they have a world class PCB production line, that ensure the fast and Quality PCB production in really very affordable rates. if you have any PCB need please try https://jlcpcb.com/IAT






Step 1: Watch Video to Know How to Make

Watch this video it will clear you how to make and operate CNC machine




Step 2: Material Required

Material Required

This are the list of some use full material required

Arduino UNO--------------------------------------QTY- 1
CNC V3 Shield------------------------------------QTY-1
servo motor----------------------------------------QTY-1
A4988 Stepper driver shield--------------------QTY-2
Old scrap DVD Drives---------------------------QTY-2
Some push buttons as limit S/W---------------QTY-2
A acrylic sheet for base
Pen holder (slavege from DVD Drive)
Some wires
Hardware like nut bots etc.



Step 3: Software Required

Software Required

Software Required

Software Required

1. Arduino IDE

GRBL LIBRARY :- Click here to download

--------------------------------------------------------------------------------------

2. INKSCAPE

SERVO CONTROL EXTENSION :-Click here to download

---------------------------------------------------------------------------------------------

3. UNIVERSAL G-CODE SENDER : - Click here to download

----------------------------------------------------------------------------------------------

Add TipAsk QuestionCommentDownload




Step 4: Machine Assembley

Machine Assembley

Machine Assembley

Machine Assembley3 More Images

Place X-axis Horizontally on the bolt mounted on acrylic sheet
Four bolt mounted on a metal sheet to fit Y-axis on it
Now place the Pen up down holder on y axis whit the help of A bolt through the center
Now place Y-axis on metal sheet and place it vertically on X-axis
Now fit servo motor so that it will move z-axis which is our pen up and down
Now mount CNC shield on Ardunino
Do wiring A shown in wiring circuit as in Next step
For better understand please watch Video & pic attached here




Step 5: Wiring Diagram

Wiring Diagram

Do wiring as shown here in image

Limit switch are optional

You can use them by changing the GRBL setting as below

$21=0 (hard limits, bool)

to

$21=1 (hard limits, bool)

Add TipAsk QuestionCommentDownload




Step 6: GRBL Loading to Arduino

GRBL Loading to Arduino

GRBL Loading to Arduino

Link to download GRBL Setup

http://www.mediafire.com/file/c36xny4qw9b7s5k/MI_G...

Download the library file unzip it

and load to arduino

Now go to File>Example>grbl upload compile and upload code to arduino

Note:- delete any previously loaded GRBL library




Step 7: G-CODE Setup in Inkscape

G-CODE Setup in Inkscape

Again we are using here INKSCAPE software to make G-code

As we are using GRBL & CNC Shield for this machine s

o it will not support a servo motor as a Z-Axis

so here some hack by doing so we can able to manage Servo works on Z-axis

you need to add MI Extension here to get it work with Z-axis Servo

Download link http://www.mediafire.com/file/nl4w871suk192x2/MI_...

after download add this files to the

inkscape directory>Share>Extension folder

Now open inkscape set page size 40 x 40mm

draw what you want to plot

select image go to convert to path

then go to extension click on MI GRBL Z-AXIS SERVO CONTORL

Servo up = M3

Servo down = M5

X-axis speed = 2000

Y-axis speed = 2000 S

ervo angle = 90

Delay = 1

Directory = as per you convenient or keep as it is

File name = as per you convenient or keep as it is

Clik on Apply now you G-code is saved @ location you mention




Step 8: GRBL Configuration & Streaming G-code

GRBL Configuration & Streaming G-code

Download link for Universal Gcode sender

https://www.mediafire.com/?2l16dvqivwgc9el

Open Universal G-code sender (Arduino must stay connected with PC/LAPTOP)

Select COM port

Set Baud rate 115200

clik on "OPEN"

go in "COMMANDS" Tab

enter $$ for GRBL configuration

Example Suppose we want to change the $0(step pulse, usec) value from 10 to 20

so enter in command line $0=20 & hit enter its done

My GRBL SETTING

$0=10 (step pulse, usec)

$1=25 (step idle delay, msec)

$2=0 (step port invert mask:00000000)

$3=0 (dir port invert mask:00000000)

$4=0 (step enable invert, bool)

$5=0 (limit pins invert, bool)

$6=0 (probe pin invert, bool)

$10=3 (status report mask:00000011)

$11=0.010 (junction deviation, mm)

$12=0.002 (arc tolerance, mm)

$13=0 (report inches, bool)

$20=0 (soft limits, bool)

$21=0 (hard limits, bool)

$22=0 (homing cycle, bool)

$23=0 (homing dir invert mask:00000000)

$24=25.000 (homing feed, mm/min)

$25=500.000 (homing seek, mm/min)

$26=250 (homing debounce, msec)

$27=1.000 (homing pull-off, mm)

$100=5.000 (x, step/mm)

$101=5.000 (y, step/mm)

$102=100.000 (z, step/mm)

$110=500.000 (x max rate, mm/min)

$111=500.000 (y max rate, mm/min)

$112=500.000 (z max rate, mm/min)

$120=10.000 (x accel, mm/sec^2)

$121=10.000 (y accel, mm/sec^2)

$122=10.000 (z accel, mm/sec^2)

$130=40.000 (x max travel, mm)

$131=40.000 (y max travel, mm)

$132=200.000 (z max travel, mm)

ok

Now time to stream Gcode to machine go to "FILE MODE" Tab Brows your gcode file and hit enter that's it

your machine start plotting Hope you like this Comment below if any doubt

