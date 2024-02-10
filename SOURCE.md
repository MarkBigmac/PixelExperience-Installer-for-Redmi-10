@echo off
color F0
title PixelExperience installer for Redmi 10 and Redmi 10 2022 (selene and eos) devices by @TechnoLoshara
mode con: lines=45 cols=128
cls
echo PixelExperience installer for Redmi 10 and Redmi 10 2022 (selene and eos) devices.
echo:
echo Please check the model of your device so that it is eos or selene, use the original wire, do not disconnect the wire durning the process and do not close this program until the end of the process. 
echo:
echo Everything you do is at your own risk.
echo:
echo By pressing any key, you agree with everything that is written above.
echo:
pause
cls
color 4
echo ----------------------------------------------------------------
echo !!! If you have a different phone model, then don't even try !!!
echo ----------------------------------------------------------------
pause
cls
color 7
echo Reboot your Redmi 10 in fastboot, and then press any button.
pause
color 2
cd platform-tools
echo Starting the process of flashing vbmeta... (If you see "< waiting for any device >" on this step, read README.txt file.)
fastboot --disable-verity --disable-verification flash vbmeta vbmeta.img
echo Rebooting in fastbootd, don't pay attention to "< waiting for any device >".
fastboot reboot fastboot
echo Starting the process of flashing the system...
fastboot flash system system.img
echo Rebooting into Recovery...
fastboot reboot recovery
cls
color F0
echo The flashing process has been successfully completed! Please select "Wipe Data" in your Recovery, and then restart your device! Enjoy your PixelExperience! ;)
echo Press any key to exit PixelExperience installer.
pause