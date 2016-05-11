#Release Notes
## 10-May-2016
1. Incorporating Changes made by Martin Zuther to implement true peak monitoring. This hasn't been documented by Martin yet but it looks like he is using 8X oversampling to get a true peak reading. There is a second peak reading at the top. 
2. Changed the deployment target in XCode to 10.4 for the AU and VST versions. The standalone would not support this so it was set to 10.5. The code was only tested on 10.11 so I can't be sure it will work on older releases especially given that there is an FFT library (FFTW) being using that was compiled using a make file. XCode reports when linking that the .a file was compiled for 10.11. AFAIK nothing in the library or the meter requires 10.11 so testing will tell. 


## 26-April-2016
	1. More Mac like. Support for Mac packages. The kmeter folder is now _inside_ the package for all three versions. You just drag a single time around now to install. Much nicer. 
	2. Built with v. 4.2.1 of the Juce library
	3. Added an icon to the standalone version. 
	4. Skin updated. Slight patterned background and a little darker. Martin and I like it, if you don't please write your suggestion for a new look on the back of a $100 bill and send it to me. I'll let Martin know.

## Orignal Release 21-April-2016
