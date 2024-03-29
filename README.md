<p align="center"><a href="https://secsels.com"><img src="https://secsels.com/wp-content/uploads/2022/04/Logo-gross.png" alt="SecSelS - Secure Selfhosted Software" width="70%" height= "auto"><a><p>
  <p margin: 35px></p>
<br>
</br>
<h1 align="center" text-align="center" display="center"><a href="https://secsels.com"><img src="https://secsels.com/wp-content/uploads/2023/01/SecSi-Energy-Monitor.png" alt="SecSi Energy Monitor" width="600px"><a></h1>

<a href="https://secsels.com">SecSelS.com</a> is a company specialized in installing, programming and inventing solutions, especially in the smart home sector. Together with <a href="https://www.luxmetering.lu/">Luxmetering</a> we invented this board to hookup every P1 meter in Luxemburg and other countries having smart meters on the P1 standard. In light of the energy-crisis and to help everyone to make his or her home or business more sustainable, we decided to opensource this device and make it compatible not only with our smart home solution, but also with other opensource smart home systems. 

You can buy a manufactured and CE-tested Version of the device for home and industry here:

<a href="https://shop.secsels.com">shop.secsels.com</a>
  

## Features List ##
###
* 2x P1 Port reader connected to Hardware-Uart -> read two meters precisely at the same time.
  * See the issues-sector for more information about encryptted meters
* Hardware-Uart Jumpers -> Use second Uart either for second P1, or for USB-C connection to program the board
* P1 Passthrough Jumper -> Connect either a second P1 device to the first P1, or directly to the ESP32
* Lan, Wifi and Bluetooth interfaces
* 2x Pulsecounter-Interface -> Hookup your watermeter or solar-system, and read the data.
* Additional GPIO's for additional sensors
* Multiple Powersupply options
  * P1 Port -> Directly get your supply from the P1 meter
  * POE -> Capable of POE powersupply
  * USB-C
###

  
## How to flash ESPHome ##
  ### Prerequisites ###
  * First make sure you have set the jumpers right for flashing. Jumpers JP7 and JP8 must be connected, UART0 is used for programming. Also make sure you don't connect any P1 device yet!
  * This tutorial is meant for the setup with <a href="https://esphome.io/">ESPHome</a>, so make sure you install it on you PC if you dont run it somewhere else. Read the guide for installing ESPHome on your PC -> https://esphome.io/guides/installing_esphome.html
  * The Yaml-Files are preprogrammed for Luxembourg, but you can alter them to work with Belgium P1 too. Also pulse counters and other devices are not included, but you can always append them to your configuration and connect them to the board. If you want to use the board for other purposes as P1 interface, you can write your own yaml of course.
  * Make sure you have <a href="https://github.com/esphome/esphome-flasher">esphome-flasher</a> installed, as the config is the easiest with that.
  * Download the <a href="#top">secsi_energy_monitor_production_lu.yaml</a> and the <a href="#top">secrets.yaml</a> to your PC.
  * If you're in Luxemburg, make sure you have your DSMR-Keys ready. In Luxemburg you can ask  your energy-provider for them per Mail.
  ### First Steps ###
  * Adjust the secrets.yaml to your data (fill in wifi data and your dsmr-key). If you don't define wifi-networks yourself but use the dashboard_import function, make sure to delete the wifi secrets.
    * On Windows you can use Notepad++ for this task, on linux use your favorite editor
    * Make sure you noted the path to your file, as you'll need it in the next step
  * Run the ESPHome commandline interface, and issue the ```run esphome secsi_energy_monitor_production_lu.yaml compile``` in your downloaded config- and secrets.yaml folder and navigate to the <NODE_NAME>/.pioenvs/<NODE_NAME>/ folder. There you will find a firmware.bin file, this is the binary you will upload.
    * Follow the instructions of the interface, and pay special attention to log output
  * Plug the Board over USB-C cable to your PC
  * Use <a href="https://github.com/esphome/esphome-flasher">esphome-flasher</a> to flash the generated config on the board. Kindly refere to their how-to.
  * If everything goes well, you now have a working P1 meter! Enjoy =)
### Additional configuration ###
  * If you use a second P1 meter, make sure to set the jumpers right! Kindly refer to the hardware documentation in the repository, and the known issues for Luxemburg
### Known issues, To be done and Limitations ###
  * When you use Ethernet, GPIO17 is not usable for external sensors/actors. He than is used as CLK_OUT so this is expected.
  
## Thank You! ##
  We wanted to thank the opensource-community and especially the developers of <a href="https://esphome.io/">ESPHome</a>! Without you, our device would not be possible! We hope that we can give back more to the community in the future. If you like our device, don't hesitate to star it =). If you don't want to configure it yourself, or have problems doing it, simply contact our company and we will find a way to help you =) -> https://secsels.com/kontakt/

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.

SecSels's logo and branding is used throughout this project. These brandings are Copyright protected by Franco Investments (SecSelS) and all rights are reserved. You may not distribute derivative works or products bearing the mentioned logos. Derivative works should remove all these brandings, and the license does not give any right of usage to these or other brandings used on the product.
