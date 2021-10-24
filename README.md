# HP_WMI with Keyboardled supports for HP OMEN 15 Laptops

This repository contains a small DKMS module containing a change to the
hp_wmi.c module from the linux kernel 5.4.0 to add keyboardleds support.

Copy the files to /usr/src/hp-wmi-1.1.0 and add to dkms.

## Read the LEDS

`cat /sys/devices/platform/hp-wmi/keyboardleds`

will return the current led status for the 4 keyboard zones

(If the keyboard leds are off this will return all #000000 - and you will have
to turn them on manually to get the status.)

## Write the LEDS

`echo "#0f84fa #710ffa #f9e50f #faac0f" | sudo tee /sys/devices/platform/hp-wmi/keyboardleds`

will change the leds to the above 4 values
