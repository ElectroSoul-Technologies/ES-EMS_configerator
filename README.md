
# ElectroSoul EMS Configerator
ElectroSoul Technologies has build an Windows compatible tool for configering an ESP32 based Wi-Fi to RS485 gateway.

Its an easy and very handy tool for configering any of our Energy Monitoring System parameters.. For details regarding our EMS product you can find [here](https://github.com/ElectroSoul-Technologies/ESP32-RS485_Gateway).
<table class="table table-hover table-striped table-bordered">
  <tr align="center">
   <td><a href="https://www.tindie.com/products/electrosoul/esp32-rs485-modbus-gateway/"><img src="https://electrosoul.in/product_photo/RS485_Gateway_WiFi/EMSv1_img1.png" width="300"></a></td>
   <td><a href="https://www.tindie.com/products/electrosoul/esp32-rs485-modbus-gateway/"><img src="https://electrosoul.in/product_photo/RS485_Gateway_WiFi/EMSv1_img2.png" width="300"></a></td>
   <td><a href="https://www.tindie.com/products/electrosoul/esp32-rs485-modbus-gateway/"><img src="https://electrosoul.in/product_photo/RS485_Gateway_WiFi/EMSv1_img3.png" width="300"></a></td>
  </tr>
 <tr align="center">
    <td><a>ElectroSoul ESP32-RS485 Gateway</a></td>
    <td><a>Connection Diagram</a></td>
    <td><a>ES Gateway Inside View</a></td>
  </tr>
  </table>
  
# Table of contents
* [FEATURES](#FEATURES)
* [Ordering INFO](#Ordering-INFO)
* [Power Requirement](#Power-Requirement)
* [GPIO Configeration Table](#GPIO-Configeration-Table)
* [ElectroSoul Dashboard](#ElectroSoul-Dashboard)
* [ElectroSoul Gateway Basic WorkFlow](#ElectroSoul-Gateway-Basic-WorkFlow)
* [ElectroSoul Gateway Configeration Tool](#ElectroSoul-Gateway-Configeration-Tool)

## Prerequisite
You need an CP2102 USB COM port driver to be installed on your machine.
You can find driver installation file inside CP2102 driver folder in repository.
For more details regarding driver you can check on  [Silicon Labs](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers)  drivers detail.

## FEATURES
  * Add/Scan  Wi-Fi credentials .
   * Multi Baudrate, Data bit, Parity, Stop bit selection.
   *  Set Retry counter.
   *  Set Timeout , Time interval between two parameter read and two slave.
   *  You can configer upto 23 diffrent electrical parameters.
   *  Upto 31 slave configeration can be done.
   *  Configeration read/ save functnality.
   * Debug option for figuring RS485.
  
## Ordering INFO
There is no additnal cost for this tool but as of now it only communicates with our own [hardware](https://github.com/ElectroSoul-Technologies/ESP32-RS485_Gateway) with our firmware on it.
We are planing to make an easy tool for you all with MQTT support and which can integrate with any MQTT broker in near future.

## How to USE
     
## ElectroSoul Gateway Configeration Tool
We have our own configeration tool for configering our EMS according to your needs.
Find more info about using configeration tool [Here]().

  <a href="http://ems.electrosoul.in/login.php/"><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/01.jpeg" width="600"></a>



