# RTL-SDR-Project
I'm using a RTL-SDR usb dongle and my own dipole antenna to pickup satellite weather images, and images from the International Space Station (ISS). The goal of this project is to be able to pickup weather images from satellites as well as images from the International Space Station. Once Im able to sucessfully able to pickup and record one of these broadcasts, I'll be able to translate these broadcasts into images. Once I've successfully done this, I can automate the process. I'll be posting images on this page. 

I used this blog to help with the construction of my antenna: https://km1ndy.com/diy-dipole-how-does-antenna-work/

The main satellites I focused on in this project were the: ISS, Meteor M2, Meteor M2-3, and Meteor M2-4. I intially wanted to start with the various NOAA satellites, (NOAA-19, NOAA-18, ect) but these satellites have been decommisioned in recent years. 

I used this website https://isstracker.pl/en/satellites/25544/passes?lat=33.46889508112487&lng=-94.01470199237441 to track the location of satellites and the approximate time I'd need to setup my antenna and begin recording. For the ISS specifically, I also used ARISS. https://www.ariss.org/upcoming-sstv-events.html ARISS shows when the ISS is transmitting SSTV (Slow Scan Television). The ISS only transmits SSTV during these specific events.

As for software, I used SDR# to visualize, recieve and demodulate radio signals transmitted by the ISS and satellites. SatDump is a program used to decode data recieved from satellites and I used it get my images. 

Frequencies used for each satellite:
ISS broadcasted at 437.550 mHz
Meteor M2 broadcasted at 137.100 mHz
Meteor M2-3 broadcasted at 137.900 mHz
Meteor M2-4 broadcasted at 137.100 mHz or 137.900 mHz 

For the ISS the signal you want to record is audio. While recording the audio on a laptop, I plan to use Robot 36. Robot 36 is a smartphone app that can decode the SSTV audio signals from the ISS. For the Meteor Satellites, IQ LRPT signals are recorded instead of audio, this offers higher resolution images than NOAA images. To recieve them, a broadband recorder in SDR# was used. 


Over the next week or two, I plan to record and signals from the previously discussed satellites and will adjust the projects scope depending on what may or may not succeed. 

Unfortunately for the time being, I was not successful in recieving a signal from the ISS. After doing further research, my dipole antenna was far from the optimal setup for recieving a signal from the ISS. My dipole was designed for satellites with much lower frequencies. I believe I could get a signal from ISS if I built a QFH (Quadrifilar Helix Antenna). At this time though, I'm not willing to spend even more money on this project. 

Even though I wasn't successful with all of my goals of this project, but I am glad it has given me a starting point in RF systems, signal processing, and communication systems in general. 

I will post notes I hand wrote while working on this project as well, they will give some more insight in my documentation of the project as well as problem solving. 
