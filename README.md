# BBAI_PinMuxing Guild

To operate Pinmux procedure, Open a terminal on BBAI and do these following steps:

1. Change directory to wherever you want to clone the next line to

`$ cd` (directory)

2. Clone BeagleBoard-DeviceTrees from github

`$ git clone https://github.com/beagleboard/BeagleBoard-DeviceTrees -b v4.14.x-ti`

3. Create and custom the device tree for beaglebone ai

`$ nano BeagleBoard-DeviceTrees/src/arm/am5729-beagleboneai-custom.dts`
(we write custom device tree for bbai here, see example to active SPI)
```
$ cd BeagleBoard-DeviceTrees  
$ make src/arm/am5729-beagleboneai-custom.dtb  
```

4. Add to uboot

```
$ sudo cp src/arm/am5729-beagleboneai-custom.dtb /boot/dtbs  
$ sudo nano /boot/uEnv.txt #(configure: dtb=am5729-beagleboneai-custom.dtb)  
$ sudo reboot  
```
 
# BBAI_PinMuxing Example (SPI active)

This BBAI compatible dts file active 2 spidev0 and spidev1 for bbai

# BBAI_PinMuxing Check
Show pin configuration (aka the pinmux) - note the pin IDs in column 2 are off due to architecture differences with the BBB
```
/opt/scripts/device/bone/show-pins.pl⏎ orshow-pins⏎
```
If you have error with this command, do `sudo apt install libinline-files-perl`
Then try again


