# Firmware for BTT SKR Mini E3 in Ender 5 Plus

Here is a working config for the Ender 5 Plus.

It requires you to load new software onto the screen. There is an SD card slot on the back side of the screen located near the main power switch. The proper software is located here: https://github.com/Neo2003/DGUS-reloaded/releases

This build disables an error related to the number of points in the Automatic Bed Leveling. The DGUS Reloaded screen software only displays a 5x5 grid correctly, but the large bed (especially if using a magnetically attached spring steel sheet) is too big for good resolution. This was done by simply commenting out the error line in Marlin/src/lcd/extui/dgus_reloaded/config/DGUS_Constants.h

In this build, the CR Touch is assumed to be connected through the Z Min endstop. If using the 5 pin "Z Probe" header, then Configuration.h needs to be adjusted at line 1307 to comment out \#define Z_MIN_PROBE_USES_Z_MIN_ENDSTOP_PIN and uncomment \#define USE_PROBE_FOR_Z_HOMING a few lines later.

The Nozzle to Probe offset is set to -1.5. This should is a safe starting point for the Microswiss nozzles, but other brands could potentially crash. Set this closer to 0 for more space if you need to before your first Z Offset calibration.

After calibrating E Steps, PID, etc, it is recommended to save this values back in to Configuration.h
