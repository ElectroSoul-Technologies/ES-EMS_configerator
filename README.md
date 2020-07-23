
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

After sucessfull instation cp2102 com port driver and our EMS software just open our EMS software.

# How to connect ?
1. Connect EMS with your machine using onboard USB  on EMS system. (Note: make sure that com port is detected on your pc by checking in device manager)
2. Now open EMS configerator and click connect icon on top right corner in EMS  software.
<a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/01.jpeg" width="600"></a>
3. On successful connection the connect icon will change and statuse will change to connected and mac address of EMS  will be displayed.
<a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/1.jpeg" width="600"></a>
(Note: sometime it may hapen that connection timeout occures and error message will pop up dont worry just press OK and try again to connect)

# How to add Wi-Fi credentials ?
1. Click on Wi-Fi Parameter button located on left pannel area.
<a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/3.jpeg" width="600"></a>
2. When clicked it will automatic scan available Wi-Fi network from device. Still you can scann network again by scan button.
3. Click your preferred  SSID and now enter Wi-Fi password and click save button.
<a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/9.jpeg" width="600"></a>
4.  Wi-Fi credentials will be stores inside EMS memory.

# How to set Serial Setting ?
1.Click on Serial Setting button located on left pannel area.
    <a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/4.jpeg" width="600"></a>
2. you can select Baud Rate, Data bit, Stop bit and Parity as per your Slave device configeration.
 <a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/8.jpeg" width="600"></a>
3. You can also set Timeout time.
4. Set number of retry if timeout accures.
5. Set time in milli second between two parameter read.
6.  Set time in milli second between two slave read. 

# How to set Slave Setting ?
1.Click on Slave Setting button located on left pannel area.
    <a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/5.jpeg" width="600"></a>
    
   2.Steps to configure slave setting:
   * First set total number of slave connected in Total Slave field.
   * Set starting slave address  in Start Device ID field.
   * Now you enable individual parameters you like or if you need all parameters enable Select All check box.
   * Now you need to set function code as per slave datasheet.
    (For Read Holding Registor set function code = 3)
    (For Read Input Registor set function code = 4)
    If all parameter function code is same you just need to set function code in Change All group box.
    *  Now set parameter  address in Address field.
    *  Now select Data type the slave will be responding.
      <a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/7.jpeg" width="600"></a>
      You can select different responce Data type it includes  different variables 16 bit unsigned integer, 32 bit unsigned integer and 32 bit floating point and different orders.
BIG ENDIAN
MID BIG ENDIAN
 LITTLE ENDIAN
MID LITTLE ENDIAN
* You can also set gain for individual parameter as an multiplying factor.
    gain value will be multiplied in the read value from the slave.
    for example: 
    Slave provides Power value as 9876 and gain is set to 0.01 then the result value will be 98.76
    
     
	        



