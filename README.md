<p align="center"><a href="https://secsels.com"><img src="https://github.com/SecSelS/assets/blob/main/copyright_protected_assets/3_PNG.png" alt="SecSelS - Secure Selfhosted Software" width="70%" height= "auto"><a><p>
  <p margin: 35px></p>
<br>
</br>
<h1 align="center" text-align="center" display="center"><a href="https://secsels.com"><img src="https://github.com/SecSelS/assets/blob/main/copyright_protected_assets/SecSi.png" alt="SecSelS - Secure Selfhosted Software" width="150px"><a> Energy Monitor</h1>

<a href="https://secsels.com">SecSelS.com</a> is a company specialized in installing, programming and inventing solutions especially in the Smart Home Sector. Together with <a href="http://hatrixelectronics.com">Hatrix Electronics</a>  and <a href="https://www.luxmetering.lu/">Luxmetering</a> we invented this board to hookup every P1 Meter in Luxemburg and other countries having Smart Meters on the P1 standard. In light of the Energy-crysis and to help everyone to make his or her home or business more sustainable, we decided to opensource this device and make it compatible not only with our smart home solution, but also with other opensource Smart Home Systems. 

You can buy a manufactured device here:

<a href="https://shop.secsels.com">shop.secsels.com</a>
  

## Features List ##
###
* 2x P1 Port reader connected to Hardware-Uart -> read two meters precicely at the same Time.
* Hardware-Uart Jumpers -> Use second Uart either for second P1, or for USB-C connection to programm the board
* P1 Passthrough Jumper -> Connect either a second P1 device to the first P1, or directly to the ESP32
* Lan, Wifi and Bluetooth interfaces
* 2x Pulsecounter-Interface -> Hokkup your Watermeter or Solar-System, and read the Data.
* Additional GPIO's for additional Sensors
* Multiple Powersupply options
  * p1 Port -> Directly get your supply from the P1 Meter
  * POE -> Capable of POE powersupply
  * USB-C
* Working with <a href="https://esphome.io/">ESP-Home</a>, but you can use every ESP32 compatible software you want
###

  
## How to flash ESP-Home ##
  ### Prerequsites ###
  * First make sure you have set the jumpers right for flashing. Jumpers JP7 and JP8 must be connected, UART0 is used for programming. Also make sure you don't connect any p1 device yet!
  * This tutorial is meant for the setup with <a href="https://esphome.io/">ESP-Home</a>, so make sure you install it on you PC if you dont run it somewhere else. Read the guide for installing ESP-Home on your PC -> https://esphome.io/guides/installing_esphome.html
  * The Yaml-Files a preprogrammed for Luxembourg, but you can alter them to work with Belgium P1 too. Also pulse counters and other devices are not included, but you can always append them to your configuration and connect them to the board. If you want to use the board for other purposes as p1 counter, you can write your own yaml of course.
  * Make sure you have esphome-flasher <a href="https://github.com/esphome/esphome-flasher">esphome-flasher</a> installed, as the config is the easiest with that.
  * Download the config yaml and the secrets yaml to your pc
  * If you're in Luxemburg, make sure you have your DSMR-Keys ready. In Luxemburg you can ask them with your energy-provider per Mail.
  ### First Steps ###
  * Adjust the secrets.yaml to your data (fill in wifi data and your dsmr-key)
    * On windows you can use notepad++ for this task, on linux use your favorite editor
    * Make sure you noted the path to your file, as you'll need it in the nex step
  * Plug the Board over USB-C cable to your PC
  * Run the ESPHOME commandline interface, and issue the run command on your downloaded config and secrets yaml https://esphome.io/guides/cli.html#run-command
    * Follow the instructions of the interface, and pay special attention to log output
  * If everything goes well, you now have a working p1 Meter! Enjoy =)
### Known Issues, To be done and Limitations ###
  * Because of the DSMR component and the encryption in Luxemburg, the second p1 port will not be interpreted by ESP-Home yet...You can use it only as passthrough at the moment
  
## Thank You! ##
  We wanted to thank the opensource-community and especially the developers of <a href="https://esphome.io/">ESP-Home</a>, and of course our Partner <a href="http://hatrixelectronics.com">Hatrix Electronics</a>! Without you our device would not be possible! We hope that we can give back more to the community in the future. If you like our device, don't hesitate to star it =). If you don't want to configure it yourself, or have problems doing it, simply contact our company and we will find a way to help you =) -> https://secsels.com/kontakt/

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">Creative Commons Attribution-ShareAlike 4.0 International License</a>.

SecSels's and Hatrix's logo and branding is used throughout this project. These brandings are Copyright protected by Franco Investments (SecSelS) and Hatrix Electronics (Hatrix) 2022 and all rights are reserved. You may not distribute derivative works or products bearing the mentioned logos. Derivative works should remove all these brandings, and the license does not give any right of usage to these or other brandings used on the product.
