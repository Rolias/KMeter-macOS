# KMeter-OSX
A Macintosh OSX version of Martin Zuther's Excellent K-Meter. Both a standalone and VST plug in. This version supports stereo. (Not 5:1) 

I'm assuming you're here because you already know what a K-Meter is and why you need one for your audio work. If you don't check out Martin's site for all the details. For now, this repo just has the binaries of the Macintosh OSX version I created. At the time the current version of OSX was 10.11.4 (El Capitain). 

You should find two zip files here. Stanalone.zip and VST_Plugin.zip. I would suggest starting with the standalone application. Unzip the folder and you will have an app called K-Meter and a folder named kmeter. These two files have to remain together. The folder contains the skins for the application. Double-click the K-Meter and it should launch. Use the _options_ button in the upper left corner and select _Audio Settings..." to set your input source. Start with something simple like your microphone. Select the K-20 button, enable peaks and set your volume. 

If you want to measure the loudness of your system audio, say from your Camtasia recording, then you'll need a tool like Soundflower than can make your output an input. Then instead of a microphone you just select soundflower as the input to the meter. 

The VST version can be used with any hosting program. Typically a DAW like Reaper. Unzip the VST_Plugin folder and again you'll have two items:
K-Meter.vst
kmeter  (a folder)

Move both of these items to any folder that your host scans for VST plugins. The default location on a Mac starts at the user library. Open a finder window. Hold down the Option key and click the Go menu and select Library. (The user library on the Mac is hidden by default, that's why you hold downt he option key). Once that windos opens navigate to:
Audio->Plug-ins->VST 
and put both items in that folder. Now start your DAW or rescan the folder. 
Here are some details on how to use it with Reaper. 
Click in the Fx box in the master track area of Reaper, Make sure "All Plugins" is selected at the top. In the filter area at the bottom type k-meter. You should now see 
VST: K-Meter (Stereo) (Martin Zuther)
Double Click that to add it to the Master Track FX panel. Double click it again in that panel to put it in a floating window. Position that floating window just to the left of your main Reaper window. Now save a new project template because you're going to want this meter to open every time you start a new project. Trust me. 
