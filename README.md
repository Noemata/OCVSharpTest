## UWP OpenCVSharp Lib and Sample

This is a quickish adaptation of OpenCVSharp (17 hours worth in the midst of other tasks) to see how easily it can be made to work with OpenCV v4.1.1 under UWP.

The original repo is located here: https://github.com/shimat/opencvsharp

The code changes in this repository have been folded back into the original.  Please use the above in future. Consider this an example only.

Support for compiled headers should really be done something like this, except this won't actually work because of precompiled header limitations:

```
#ifdef _WINRT_DLL
#include "pch.h"
#endif
#include "aruco.h"
```

Any thoughts?

## Building

1. Use vcpkg to get OpenCV for uwp

.\vcpkg install opencv[contrib]:x64-uwp --recurse

2. Adjust project settings to reference where things land on your system

3. Do a diff to see what was changed

### Screenshot
![Screenshot](https://github.com/Noemata/OCVSharpTest/raw/master/Screenshot.png)

** The above shows the Microsoft CameraOpenCV sample converted to be entirely in C#.  This still needs a little more clean up.
