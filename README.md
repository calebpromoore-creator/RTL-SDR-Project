# RTL-SDR-Project
I'm using a RTL-SDR usb dongle and my own dipole antenna to pickup satellite weather images, and images from the International Space Station (ISS). The goal of this project is to be able to pickup weather images from satellites as well as images from the International Space Station. Once Im able to sucessfully able to pickup and record one of these broadcasts, I'll be able to translate these broadcasts into images. Once I've successfully done this, I can automate the process. I'll be posting images on this page. 

I used this blog to help with the construction of my antenna: https://km1ndy.com/diy-dipole-how-does-antenna-work/

The formula for calculating the length of the dipole legs is: L = 468/F(mHz) So, this is 468/ divided by the desired frequency you wish to recieve a signal from. So for the ISS, I needed to tune into 437.550 mHz so 468/437.550 is 1.07ft. Divide that between two legs, and you get 6.4 in for each leg. For the Meteor satelites the frequency is relatively similar, so I did 468/137.1Mhz and got 40.92 in and 20.46 in for each dipole leg. 

The main satellites I focused on in this project were the: ISS, Meteor M2, Meteor M2-3, and Meteor M2-4. I intially wanted to start with the various NOAA satellites, (NOAA-19, NOAA-18, ect) but these satellites have been decommisioned in August 2025. 

I used this website https://isstracker.pl/en/satellites/25544/passes?lat=33.46889508112487&lng=-94.01470199237441 to track the location of satellites and the approximate time I'd need to setup my antenna and begin recording. For the ISS specifically, I also used ARISS. https://www.ariss.org/upcoming-sstv-events.html ARISS shows when the ISS is transmitting SSTV (Slow Scan Television). The ISS only transmits SSTV during these specific events.

As for software, I used SDR# to visualize, recieve and demodulate radio signals transmitted by the ISS and satellites. SatDump is a program used to decode data recieved from satellites and I used it get my images. 

Frequencies used for each satellite:
ISS broadcasted at 437.550 mHz
Meteor M2 broadcasted at 137.900 mHz
Meteor M2-3 broadcasted at 137.900 mHz
Meteor M2-4 broadcasted at 137.900 mHz
I used a local NOAA test frequency to test my antenna. The frequency was 162.550 mHz  

For the ISS the signal you want to record is audio. The audio recorder in SDR# is used. Make sure that SDR# audio is output through  While recording the audio on a laptop, I plan to use Robot 36. Robot 36 is a smartphone app that can decode the SSTV audio signals from the ISS. For the Meteor Satellites, IQ LRPT signals are recorded instead of audio, this offers higher resolution images than NOAA images. To recieve them, a broadband recorder in SDR# was used. 

Orbitron is another important piece of software for this project. The program allows you to track the location of satellites in real time. This gives you an idea of when and where the satelitte will appear. I used this with all the satellites in this project. SDR# has a plugin that allows it to connect with Obitron. This allows for real time tracking of the satellite's frequency. A satellite's frequency shifts slightly as it shifts, the satellites frequency lightly shifts. This is called a Doppler shift. This plugin with Orbitron allows for a smoother signal to be recorded. 

Link to the plugin: https://fuzzthepiguy.tech/tracking-plugin/
This site was also helpful when setting up Orbitron: https://usradioguy.com/meteor-satellite/#dde

Some important settings I used in SDR#:
In the radio tab: 
NFM (Narrowband Frequency Modulation) This is the mode I used. This was used for the ISS and Meteor Satellites
I set the bandwidth to 140k for the the Meteor satellites and 25k for the ISS. 
Turned off the squelch setting to reduce noise/interference
In the source tab: turn off AGC, change the sample rate to 2.048 MSPS, change the sampling mode to quadrature sampling, turn on offset tuning, RF Gain should be 35-40 dB, Correction should be around 10-15 ppm or -5 to -15 ppm This largly depends on where the signal is on it's pass. The red line is where your signal is and you want to line it up with the black one, this can be done with correction. The correction has to be adjusted throught the pass. This is to avoid the noise spike and get a clean/clear signal, and turn on the correct IQ setting. 
When using the Tracking DDE client, make sure you setup the satellite settings and and check the desired satellite and use the SDR# driver to connect to the satellite and track it in real time. 

When going for a satellite pass I typically check the date, time, and elavation of the desired satellite.
10-15 minutes before the pass, get your laptop and antenna setup. You ideally want to be outside when doing this. SDR# should have all the proper settings, and two minutes before the pass begin recording audio/IQ. Then before the pass begins, I make sure my antenna legs are straight and the coax cable is stretched out. Knowing the elevation angle should give you a good idea on where to point your antenna. A low angle like 20 degrees is toward the horizon and a high angle like 90 degrees is directly above you.  As the pass goes you will have to slowly turn your antenna so you can continue to pickup the signal and get a clean image. Once you pickup the signal youll probably have to use a positive or negative correction in order to center the signal. I repeat this process over the whole pass, adjusting my antenna and correction throughout. Continue to record two minutes after the pass as well. You than stop recording and youll have a .wav file. 

In SatDump, you than use Meteor M2-x LRPT to decode the .wav file. The input will be your input file and the output is in afolder of your own choosing. (I make a seperate folder for this). You should then be able to have SatDump decode and demodulate the file and if your successful, you'll have an image in the selected folder. 

This is a very delicate process, and you are likely to fail dozens of times before you get a successful image. Use trial and error and make small adjustments. 

Over the next week or two, I plan to record and signals from the previously discussed satellites and will adjust the projects scope depending on what may or may not succeed. 

Unfortunately for the time being, I was not successful in recieving a signal from the ISS. After doing further research, my dipole antenna was far from the optimal setup for recieving a signal from the ISS. My dipole was designed for satellites with much lower frequencies. I believe I could get a signal from ISS if I built a QFH (Quadrifilar Helix Antenna). At this time though, I'm not willing to spend even more money on this project. I have also decided to drop the Meteor M2 satellite because I couldnt recieve a strong signal consistently. Meteor M2-3 and M2-4 give me consistently strong signals in my area.  

Even though I wasn't successful with all of my goals of this project, but I am glad it has given me a starting point in RF systems, signal processing, and communication systems in general. 

I will post notes I hand wrote while working on this project as well, they will give some more insight in my documentation of the project as well as problem solving. 

If I was to do this project again, I'd need to have a higher budget. This would allow me to build a more powerful antenna that would have an easier time recieveing and keeping a signal. I'd also like to try a more remote area for my passes. I have done all the passes outside my house where there can be interference. 
