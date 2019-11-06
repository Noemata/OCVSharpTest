## UWP OpenCVSharp Sample (not fully working)

This is a very quick hack (2 hours worth) on OpenCVSharp to see how easily it can be made to work with OpenCV v4.1.1 under UWP.

Many aspects of the code are working, but no attempt was made to get things right so consider this just a starting point.

If you do fix the remaining issues, please leave a note in the issues section here.

This dumb hack was made to the OpenCV cvdef.h header, not sure why adding _WIN32 def didn't work.

```
#ifndef CV_EXPORTS
#   define CV_EXPORTS __declspec(dllexport)
//# define CV_EXPORTS
#endif
```

Changed to a not so dumb hack in pch.h instead of above, so no need to change anything in OpenCV.  OpenCVSharp is also a drop in, no changes needed. (No longer true, very minor tweaks were needed, just look for MP! in code)

```
#define CV_EXPORTS __declspec(dllexport)
```

Support for compiled headers should really be done something like this, except this won't actually work because of precompiled header limitations:


```
#ifdef _WINRT_DLL
#include "pch.h"
#endif
#include "aruco.h"
```

## Building

1. Use vcpkg to get OpenCV for uwp

.\vcpkg install opencv[contrib]:x64-uwp --recurse

2. Adjust project settings to reference where things land on your system

3. Do a diff to see what was changed

4. Don't use this code in a production setting

### Screenshot
![Screenshot](https://github.com/Noemata/OCVSharpTest/raw/master/Screenshot.png)

** The above shows the Microsoft CameraOpenCV sample converted to be entirely in C#.  This still needs a little more clean up.

*** Note, am 10 hours into the hack for UWP support in OpenCVSharp. It is now somewhat less hackish and fairly usable.  Hopefully the original author of OpenCVSharp can take it from here.