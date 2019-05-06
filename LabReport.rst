Team#0 Lab Report
*****************
Board History
=============
------------
Bobby Galvan
------------

The Raspberry Pi Zero WH is Raspi's newest edition of their budget Zero boards and 
is the successor to the Pi Zero W. The WH stands for wireless with headers. The
Raspberry Pi boards were originally designed to be teaching tools for schools 
and colleges, however they were quickly adopted by maker communities as hobby boards.

The founders of Raspberry Pi sought to solve the "programming gap" in the UK and 
in developing countries with an extremely low-cost computer, the first of which was 
the Pi 1 model B in 2012. Quickly, hobbyists saw endless applications for the 
computer from a "beet box" that uses capacitive sensors to trigger audio to a low-cost
portable retinal camera used to treat patients in rural areas of India.

The pi zero was specifically designed to be a "budget budget" board, and the first 
iteration was released in 2015. The W was the second version, and allowed for wifi
usage, and the WH model allows for a more out-of-the-box experience without the
need for soldering to the board.

Basic Board Setup
=================
-------------
Leslie Durkey
-------------
To power the Raspberry Pi Zero WH, the standard accessories are a microSD card,
mini-HDMI cable, a micro-USB cable for power and another for mouse and keyboard 
input, however our team decided to modify the OS image to enable ssh, or secure 
shell, which allowed us to enable virtual network computing, or VNC, through PuTTY. 
Ultimately, we only needed the micro-USB connected to the input port to power 
the Raspberry Pi to then remote in.

Without ethernet cable port on the Zero WH, utilizing the HypriotOS would have 
been extremely difficult as there seems to be no way, or no way we've found,
to access the Pi through an ssh specifically on this OS without finding the IP
address first on a Windows machine

First, we flashed the Raspian OS image onto the microSD card with Balena Etcher,
modified the config.txt file and the cmdline.txt file, and finally adding an 
empty file titled ssh to bypass Raspian's default ssh disabled status.

Second, to access the VNC we needed Bonjour print services for Windows 
which acts as a zeroconf (zero-configuration network) to allow the automatic 
discovery of the Raspi system over the local network.

While this step wasn't necessary, we used PuTTY to access the OS and to enable 
VNC, which then allowed us to view the image remotely through a VNC viewer.

Development Tools
=================
------------
Bobby Galvan
------------

The bare bones tools needed to utilize the Raspberry Pi for development 
are a compiler and editor. We chose the GCC, the GNU compiler and the 
GNU nano editor.

While an IDE is certainly not necessary to write simple programs, we
decided to install one that supports C++, specifically the Geany IDE.
As we continue our group projects with the Raspberry Pi, it seemed 
only prudent to have a robust development suite.

*C++ Hello World Source:*

.. image:: https://i.imgur.com/W7J0mLa.png

*Python Hello World Source:*

.. image:: https://i.imgur.com/zqoycRa.png

*C++ and Python Hello World Output:*

.. image:: https://i.imgur.com/ipeUVjc.png

Processor Architecture
======================
--------------
Eri Midorikawa
--------------

.. image:: https://media.discordapp.net/attachments/549363585705574420/560193234597314570/2019-03-26_3.23.29.png?width=831&height=676

Raspberry Pi Zero uses Broadcom BCM2835 SoC. This processor includes ARM1176JZF-S 
as CPU. The ARM1176JZF-S processor incorporates an integer core that implements 
the ARM11 ARM architecture v6. It supports the ARM and Thumb instruction sets, 
Jazelle technology to enable direct execution of Java bytecodes, and a range of 
SIMD DSP instructions that operate on 16-bit or 8-bit data values in 32-bit 
registers. This processor includes Vector Floating-Point (VFP) coprocessor support.

Processor Assembly Language
===========================
------------
Shaun Peretz
------------

The ARM11 is 32 bit architecture, and includes Arm and Thumb instructions sets.
The ARM implements 32-bit long instructions and can manipulate 32 bit integers. 
Therefore, most instructions are executed in one cycle. Many of the ARM 
instructions can be executed conditionally. Unlike ARM instruction set, Thumb 
instructions are primarily unconditional. Thumb implements a 16-bit instruction 
set on a 32-bit architecture, which enables higher performance due to a higher code density.

Demonstration Project: Javascript Playground
============================================
-------------
Leslie Durkey
-------------

For the demo project, we made a Node.js application which utilizes a Docker 
container to experiment with and execute Javascript code. The first step 
after Docker installation was to install an ARM image, specifically an image
made by Resin.io which is supported on the Raspberry Pi, to be able to make a
container. Next, we built a container which used Resin.io's Raspbian image 
as a base which pulls down Node from the official Node.js website. Finally, 
we built and ran it! 

*Demo Javascript code that sends a get request to NASA's API and prints
the description for the astronomy photo of the day:*

.. image:: https://i.imgur.com/6y4XQw5.png

*Output:*

.. image:: https://i.imgur.com/aBj4QIU.png
