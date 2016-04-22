# KMeter-OSX
A Macintosh OSX version of Martin Zuther's Excellent K-Meter. Both a standalone and VST plug in. This version supports stereo (not 5.1) only.

If you don't know what a K-Meter is check out [Martin's site](http://www.mzuther.de/en/software/kmeter/) for all the details. For now, this repo just has the binaries of the Macintosh OSX version I created. At the time the current version of OSX was 10.11.4 (El Capitain). 

Download the K-Meter-Dist.zip file. It wil contain:
* KMeter_manual.pdf
* Standalone (folder)
  * K-Meter
  * kmeter (folder)
* VST_Plugin (folder)
  * K-Meter.vst
  * kmeter (folder)
Yep, the same folder is in there twice, wasteful but it lets you drag and drop things to two different locations. 

## Standalone
 The application and the kmeter folder have to remain together. Most people will put these two things in their Application folder but you don't have to. The _kmeter_ folder contains the skins for the application. Double-click the K-Meter application and it should launch. Use the _options_ button in the upper left corner and select _Audio Settings..._ to set your input source. Start with something simple like your microphone. Select the K-20 button, enable peaks and set your volume. 

If you want to measure the loudness output of your system audio, say from a tool like Camtasia, then you'll need a tool like Soundflower that can make your output into an input. Then instead of a microphone you just select Soundflower as the input to the meter. 

## VST Plug-in
The VST version can be used with any hosting program that supports the VST format, e.g. a DAW like [Reaper](http://www.reaper.fm/). Take the two items:  
* K-Meter.vst
* kmeter  (a folder)
and  move both of them to any folder that your host scans for VST plugins. The default location on a Mac _(that all hosts should scan by default)_ starts at the user library (i.e. ~/Library). Open a finder window. Hold down the Option key and click the Go menu and select Library. _The user library on the Mac is hidden by default, that's why you hold downt he option key._ Once that window opens navigate to:  
**Audio->Plug-ins->VST**   
and put both items in that folder.  
Now start your DAW or rescan the folder. Here are some details on how to use the K-Meter with Reaper:   
1. Click in the **Fx** box in the master track area of Reaper. 
2. In the resulting dialog make sure _All Plugins_ is selected at the top. 
3. In the filter area at the bottom type k-meter. 
4. You should now see VST: K-Meter (Stereo) (Martin Zuther)
5. Double Click that to add it to the Master Track FX panel. 
6. Double click it again in that panel to put it in a floating window. 
7. Position that floating window just to the left of your main Reaper window. 
8. Now save a new project template because you're going to want this meter to open every time you start a new project. Trust me. 

### Want to Know More?
Read the manual. 

### Just How Geeky Are You?
I'm also including all the validation files so you can validate the meter does what it says it does. 

### For the Terminally Curious
The standalone version doesn't look like a normal Macintosh application. The entire project (VST and Standalone) relies on the [JUCE framework](https://www.juce.com/). The program also uses the [Fastest Fourier Transform in the West (fftw)](http://www.fftw.org/) library.  
