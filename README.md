# RTL-SDR-Project
I'm using a RTL-SDR usb dongle and my own dipole antenna to pickup satellite weather images, and images from the International Space Station (ISS). The goal of this project is to be able to pickup weather images from satellites as well as images from the International Space Station. Once Im able to sucessfully able to pickup and record one of these broadcasts, I'll be able to translate these broadcasts into images. Once I've successfully done this, I can automate the process. I'll be posting images on this page. 

I used this blog to help with the construction of my antenna: https://km1ndy.com/diy-dipole-how-does-antenna-work/

The formula for calculating the length of the dipole legs is: L = 468/F(mHz) So, this is 468/ divided by the desired frequency you wish to recieve a signal from. So for the ISS, I needed to tune into 437.550 mHz so 468/437.550 is 1.07ft. Divide that between two legs, and you get 6.4 in for each leg. For the Meteor satelites the frequency is relatively similar, so I did 468/137.1Mhz and got 40.92 in and 20.46 in for each dipole leg. 

The main satellites I focused on in this project were the: ISS, Meteor M2, Meteor M2-3, and Meteor M2-4. I intially wanted to start with the various NOAA satellites, (NOAA-19, NOAA-18, ect) but these satellites have been decommisioned in recent years. 

I used this website https://isstracker.pl/en/satellites/25544/passes?lat=33.46889508112487&lng=-94.01470199237441 to track the location of satellites and the approximate time I'd need to setup my antenna and begin recording. For the ISS specifically, I also used ARISS. https://www.ariss.org/upcoming-sstv-events.html ARISS shows when the ISS is transmitting SSTV (Slow Scan Television). The ISS only transmits SSTV during these specific events.

As for software, I used SDR# to visualize, recieve and demodulate radio signals transmitted by the ISS and satellites. SatDump is a program used to decode data recieved from satellites and I used it get my images. 

Frequencies used for each satellite:
ISS broadcasted at 437.550 mHz
Meteor M2 broadcasted at 137.100 mHz
Meteor M2-3 broadcasted at 137.900 mHz
Meteor M2-4 broadcasted at 137.100 mHz or 137.900 mHz
I used a local NOAA test frequency to test my antenna. The frequency was 162.550 mHz  

For the ISS the signal you want to record is audio. While recording the audio on a laptop, I plan to use Robot 36. Robot 36 is a smartphone app that can decode the SSTV audio signals from the ISS. For the Meteor Satellites, IQ LRPT signals are recorded instead of audio, this offers higher resolution images than NOAA images. To recieve them, a broadband recorder in SDR# was used. 

Orbitron is another important piece of software for this project. The program allows you to track the location of satellites in real time. This gives you an idea of when and where the satelitte will appear. I used this with all the satellites in this project. SDR# has a plugin that allows it to connect with Obitron. This allows for real time tracking of the satellite's frequency. A satellite's frequency shifts slightly as it shifts, the satellites frequency lightly shifts. This is called a Doppler shift. This plugin with Orbitron allows for a smoother signal to be recorded. 

Link to the plugin: https://fuzzthepiguy.tech/tracking-plugin/
This site was also helpful when setting up Orbitron: https://usradioguy.com/meteor-satellite/#dde

Over the next week or two, I plan to record and signals from the previously discussed satellites and will adjust the projects scope depending on what may or may not succeed. 

Unfortunately for the time being, I was not successful in recieving a signal from the ISS. After doing further research, my dipole antenna was far from the optimal setup for recieving a signal from the ISS. My dipole was designed for satellites with much lower frequencies. I believe I could get a signal from ISS if I built a QFH (Quadrifilar Helix Antenna). At this time though, I'm not willing to spend even more money on this project. 

Even though I wasn't successful with all of my goals of this project, but I am glad it has given me a starting point in RF systems, signal processing, and communication systems in general. 

I will post notes I hand wrote while working on this project as well, they will give some more insight in my documentation of the project as well as problem solving. 
