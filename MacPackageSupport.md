#Support for Mac Packages
Mac applications are actually glorified folders. It's possible to right click on the application and select "Show Package Contents". That allows me to navigate down the path to Contents/MacOS and put a kmeter folder right next to the executable file. Now users on the Mac can't screw up when installing. They just drag the stanadalone app to the Mac applications folder and the VST or AU to their respective folders and everything works. You will note I check for ```__Apple__``` so this should have no effect on the Windows or Linux versions. 

## plugin_parameters.h
```c++
//in the public: area add a new static method
static const File getSkinDirectory(); 
```
##plugin_parameters.cpp
### Implement the new method
```C++
//Implement the new method
// ========== Mac Package Support Modification ==========
// Created method for setting skin directory since this value is also used
// by plugin_editor.cpp
// author: Tod Gentille  teg
const File KmeterPluginParameters::getSkinDirectory()
{   
    File applicationDirectory;
    // On all platforms we want the kmeter/skins folder to be located with the executable.
    // On the Mac the executable is NOT the same as the application folder because on the mac
    // what looks like an application is really a package (i.e. a folder) the executable is buried
    // inside that. When deploying on a Mac right-click on the build target and select "Show Package Contents"
    // navigate through Contents/MacOS and you will find the K-Meter executable. Put the kmeter folder here.
#ifdef __APPLE__
    applicationDirectory = File::getSpecialLocation(File::currentExecutableFile).getParentDirectory();
#else
    applicationDirectory = File::getSpecialLocation(File::currentApplicationFile).getParentDirectory();
#endif
    
   return applicationDirectory.getChildFile("./kmeter/skins/");
}
//========== End Mac Package Support Modification ==========
```
### Use the new method
At line 165 you have the comment and line shown here  
```c++
// the following may or may not work on Mac
File applicationDirectory =  
File::getSpecialLocation(File::currentApplicationFile).getParentDirectory();
```
Delete the comment and replace the line of code with  
```c++
File skin_directory = getSkinDirectory();
```
##plugin_editor.cpp
In the constructor you have the same comment and line of code so replace that one too. Since we are in another class the syntax is slightly different  
```c++
  skinDirectory = KmeterPluginParameters::getSkinDirectory();
  ```
  
