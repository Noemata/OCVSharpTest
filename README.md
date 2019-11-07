## UWP OpenCVSharp Sample (not fully working)

This is a quickish adaptation of OpenCVSharp (17 hours worth in the midst of other tasks) to see how easily it can be made to work with OpenCV v4.1.1 under UWP.

The original repo is located here: https://github.com/shimat/opencvsharp

Surprisingly little tweaking was required to support UWP because of the exceptional work done by the author of OpenCVSharp and vcpkg.  This isn't a fork because it initially started as a hack with no expectation of success.  Hopefully the author of OpenCVSharp will do the integration back into the main repo.

Most aspects of the code are working, at least everything tried so far, but there are still some rough edges in WinRT implementation details.  Also some parts of OpenCV are not available with vcpkg.

If you do fix the remaining issues, please leave a note in the issues section here.

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

4. Don't use this code in a production setting

### Screenshot
![Screenshot](https://github.com/Noemata/OCVSharpTest/raw/master/Screenshot.png)

** The above shows the Microsoft CameraOpenCV sample converted to be entirely in C#.  This still needs a little more clean up.
