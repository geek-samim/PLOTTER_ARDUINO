# PLOTTER_ARDUINO
Hello friends in this post we will see how to make mini CNC plotter machine using old scrap DVD drives, arduino & L293D motor shield.
In fact in past I have build some arduino mini CNC plotter machine or drawing machine in past.
But those projects are not well documented and unclear so I got many request to make a detail in depth tutorial about how to make arduino based mini CNC plotter machine.
So in this post I an going to cover all points like hardware assembly, code for arduino, processing GUI, G-code generation etc.
So before moving further let me brief you about what is CNC plotter machine is.


 


OVERVIEW
CNC plotter machine is basically a 2.5 axis CNC machine, it have two stepper motor on both X & Y axis and a servo motor at Z axis.
A pen is connected on Y-axis ans Z-axis is used to make pun up & down.
As name suggest plotter machine obvious draw or plotting a drawing as per given instruction.
To give instruction to machine what to draw a special type of code called G-code is required.
Image will be converted to G-code with the help of special type of software.
afterwards this G-code sends to controller and controller commands motors how to move.
As result machine will draw image on paper.
Now lets we will see how to build such machine. starting with material list

# MATERIAL LIST
Sr No.	ITEM	QTY
1	Scrap DVD Drive	2
2	Arduino UNO	1
3	L293D MOTOR SHIELD	1
4	MINI SERVO MOTOR	1
5	5V 1Amps POWER ADAPTER	1
6	SOME WIRES FOR MOTOR CONNECTION	—-
7	NUT AND BOLTS AS REQUIRED	—-
SOFTWARE LIST
1	ARDUNIO IDE
2	PROCESSING IDE
3	INKSCPAE VERSION 0.48.5
Please download the software from above link, and install them on your PC.

# CODE AND LIBRARY
1	CNC CODE FOR ARDUINO
2	GCTRL PROCESSING CODE
3	AFMOTOR LIBRARY FOR ARDUINO
4	Makerboat Gcode Inkscape extension
“CNC CODE FOR ARDUINO” needs to be upload on arduino.
“GCTRL” needs to be open in processing software.
“AFMOTOR” library need to add in arduino IDE
how to do all this ? we’ll see further.

# MACHINE ASSEMBLY
# Step 1.
DVD drive to make mini CNC plotter machien
To make Arduino based mini CNC plotter machine obviously we need two scrap DVD drive.
I purchased this drive from local computer repairing shop in less then 1$ .
we’ll going to use its stepper motor along with sliding mechanism
here note that not all DVD drives have stepper motor in it. if the motor have 4 wires it means it is a stepper motor.
if you not found any 4 wire motor in DVD drive then it is use less.

# Step 2.



I quickly unscrew the DVD drive case with the help of screw driver and by applying some force I take out the stepper motor mechanism from the DVD drive case.
In this way I have two stepper driver mechanism and two empty case of DVD drive.

# Step 3.



After taking out stepper motor mechanism I cut the default motor connector strip with the help of scissor.
then I bring some DuPont 4 wire of around 40 cm and cut it into 2 pieces one for each stepper motor connection.
Then I strip the wire carefully without damaging the copper strain of wire.
and solder it to the expose terminals of stepper motor.


 



# Step 4.
Here I have paint the the empty case of DVD drive using gray shade spray paint, this step is not compulsory its ok if you don’t want to paint them.




Then I used a piece of 20 x 20 mm aluminium angle to make holder for X-axis and Y-axis .
I drill the 5mm hole on the aluminium piece and cut it into two piece of clamp, further I use this clamp to fix the both axis with the help of M5X10 nut and bolt.

# Step 5.


Now I am marking for hole on DVD drive case to make arrangement for mounting for both stepper motor mechanism.
I carefully drill the hole of 5mm with the help of drill machine.

# Step 6.



After drilling the hole in DVD drive case I fix the four M4 X 60 nut bolts at the four corner of stepper motor mechanism.
Now I placed the stepper motor mechanism to its place and secure all four bolts with M4 nuts.

# Step 7.








This the is most important step in making mini Arduino CNC plotter machine here we are making pen up and down mechanism.
First I take a compass and carefully remove its pen holder part.
then I used a simple pen with top and bottom openable.
first take out the refill of pen and cut about 2 cm part from the top of the refill.
now I place a spring at the top of the refill which I have salvage from other trigger type pen.
then I used a strong thread and tied it to the center of the refill and secure it with super glue on to its place.
now I make a small hole just above from the center of pen body.


Now I carefully place the refill inside the pen and passed thread outside from the hole.
In this way I made my pen up down mechanism, when I pull the thread pen refill push upward and when I release the thread refill went down.
and due to the spring attached at top of the refill pen tip will maintain a good friction with paper..
Pen is now placed in pen holder and glue it with super glue on the X-axis



I attached a mini servo at X-axis and tie the thread with the knob of mini servo motor.

# Step 8.



I drill four hole on the back side of machine and screw four 15mm spacer to mount arduino UNO onto it.
L293D motor shield is mounted on Arduino UNO.
In this way assembly of Arduino CNC plotter machine is competed now we will see the wiring


 
# WARNIRING
Wiring drawing for mini CNC plotter machiNE
We are using Arduino UNO as a brain of CNC machine, as we know there is stepper motors used in CNC machine.
Stepper motors are not easy to control so here we are using a L293D motor shield to control our stepper motors and one servo motor is used for pen up down movement.

Before start wiring first we nee to the know the correct wire of stepper motor.
Our stepper motor have 4 wire and stepper motor have two coils means the a set of two wire is form one coil.
so we need to find out which two wires are from one coil, so here I am using multimeter keeping multimeter on continuity test.
I connect the mutimeter prob to the wires one by one, if I get continuity( few ohms) between any two wires means that both wires belong to single coil and rest two are from other coil.

dvd drive stepper motor testing


Don’t forget to remove that yellow jumper, and connect the stepper motor wires as shown in drawing above.
and also connect the servo motor at servo 1 terminal of L293D Motor shield.
You need a power adapter to feed power to the machine, you can use 5VDC 1amps power adapter.
In this way wiring is completed now we can move towards arduino code uploading process.

