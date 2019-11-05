## UWP OpenCVSharp Sample (not fully working)

This is a very quick hack (2 hours worth) on OpenCVSharp to see how easily it can be made to work with OpenCV v4.1.1 under UWP.

Many aspects of the code are working, but no attempt was made to get things right so consider this just a starting point.

If you do fix the remaining issues, please leave a note in the issues section here.

## Building

1. Use vcpkg to get OpenCV for uwp

.\vcpkg install opencv[contrib]:x64-uwp --recurse

2. Adjust project settings to reference where things land on your system

3. Do a diff to see what was changed

4. Don't use this code in a production setting
