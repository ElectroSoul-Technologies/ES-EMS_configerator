

# ElectroSoul EMS Configerator
ElectroSoul Technologies has built a Windows compatible tool for configuring an ESP32 based Wi-Fi to RS485 gateway.

Its an easy and very handy tool for configering any of our Energy Monitoring System parameters.. For details regarding our EMS product you can find [here](https://github.com/ElectroSoul-Technologies/ESP32-RS485_Gateway).
  
# Table of contents
* [FEATURES](#FEATURES)
* [Ordering INFO](#Ordering-INFO)
* [How to connect?](#How-to-connect )
* [How to add Wi-Fi credentials?](#How-to-add-Wi-Fi-credentials )
* [How to set Serial Setting?](#How-to-set-Serial-Setting)
* [How to do Debugging?](#How-to-do-Debugging )


## Prerequisite
You need a CP2102 USB COM port driver to be installed on your machine.
You can find the driver installation file inside the CP2102 driver folder in the repository.
For more details regarding the driver, you can check on  [Silicon Labs](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers)  drivers detail.

## FEATURES
  * Add/Scan  Wi-Fi credentials .
   * Multi Baudrate, Data bit, Parity, Stop bit selection.
   *  Set Retry counter.
   *  Set Timeout, Time interval between two parameters read and two slaves.
   *  You can configure up to 23 different electrical parameters.
   *  Up to 31 slave configuration can be done.
   *  Configeration read/ save functnality.
   * Debug option for figuring RS485.
  
## Ordering INFO
There is no additional cost for this tool but as of now it only communicates with our own [hardware](https://github.com/ElectroSoul-Technologies/ESP32-RS485_Gateway) with our firmware on it.
We are planning to make an easy tool for you all with MQTT support and which can integrate with any MQTT broker in the near future.

After successful installation cp2102 com port driver and our EMS software just open our EMS software.

# How to connect?
1. Connect EMS with your machine using onboard USB  on the EMS system. (Note: make sure that comport is detected on your pc by checking in device manager)
2. Now open EMS configurator and click connect icon on the top right corner in EMS  software.
<a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/1.jpeg" width="600"></a>
3. On a successful connection, the connect icon will change and status will change to connected and the mac address of EMS  will be displayed.

<a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/01.jpeg" width="600"></a>

(Note: sometime it may happen that connection timeout occurs and the error message will pop up don't worry just press OK and try again to connect)

# How to add Wi-Fi credentials?
1. Click on Wi-Fi Parameter button located on left pannel area.
<a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/3.jpeg" width="600"></a>
2. When clicked it will automatically scan available Wi-Fi networks from the device. Still, you can scan the network again by scan button.
3. Click your preferred  SSID and now enter Wi-Fi password and click save button.
<a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/9.jpeg" width="600"></a>
4.  Wi-Fi credentials will be stores inside EMS memory.

# How to set Serial Setting?
1.Click on the Serial Setting button located on the left panel area.
    <a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/4.jpeg" width="600"></a>
2. you can select Baud Rate, Data bit, Stop bit and Parity as per your Slave device configeration.
 <a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/8.jpeg" width="600"></a>
3. You can also set Timeout time.
4. Set number of retry if timeout accures.
5. Set time in milli second between two parameter read.
6.  Set time in milli second between two slave read. 

# How to set Slave Setting?
1.Click on the Slave Setting button located on the left panel area.
    <a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/5.jpeg" width="600"></a>
    
   2.Steps to configure the slave setting:
   * First set a total number of slaves connected in the Total Slave field.
   * Set starting slave address in Start Device ID field.
   * Now you enable individual parameters you like or if you need all parameters to enable Select All checkbox.
   * Now you need to set function code as per slave datasheet.
    (For Read Holding Registor set function code = 3)
    (For Read Input Registor set function code = 4)
    If all parameter function code is same you just need to set function code in Change All group box.
    *  Now set parameter address in Address field.
    *  Now select Data type the slave will be responding.
      <a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/7.jpeg" width="600"></a>
      You can select different response Data types it includes different variables 16-bit unsigned integer, 32-bit unsigned integer, and 32-bit floating-point and different orders.
BIG ENDIAN
MID BIG ENDIAN
 LITTLE ENDIAN
MID LITTLE ENDIAN
* You can also set gain for the individual parameters as a multiplying factor.
    the gain value will be multiplied in the read value from the slave.
    for example: 
    Slave provides Power value as 9876 and gain is set to 0.01 then the result value will be 98.76
* Now you can do same type of all settings for different slaves by changing Select Slave No. On the top right corner if all slaves require different settings.
* If all slave are same and you want to read the same parameters from all slave then no need to configure settings for all slave just check All Slave Are Same and now you only need to configure for slave 1 and rest of slave will be configured same as slave 1.

# How to do Debugging?
In many cases, due to less documentation of slave devices, it may happen that it causes confusion such as
* Which value to be used as Function Code for reading data?
* RS485 Address given in datasheet needs to decrement by 1 or not?
* What will be response type it may be 16bit uint, 32bit uint or 32bit float we don't know if datasheet of a slave does not mention it.
*   What will be response order like big-endian, little-endian, mid-big-endian or mid-little-endian we don't know if datasheet of the slave does not mention it.
* What will be the gain?

So for easy debugging such an issue, you can connect RS485 cables between EMS device and Slave device and open the Debugging tab.
 <a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/6.jpeg" width="600"></a>

* Now you need to enter slave ID.
* Now if you know Function Code select it or if not just pick random 3 or 4.
* Now if you have datasheet the select such address that you know what will be result value such as frequency will be near 50/60 or line to neutral voltage address value will be near 230. Don't worry about address offset now just use the address mentioned in the datasheet.
* Now comes tricky part Data type selection. So there are few possibilities.
	* You know that data will come in 16bit uint, 32bit uint or 32bit floating point so you just need to figure out data order. So don't worry about data order select any as of now.
	* If you don't know above point then you need to do Try and error approach :neutral_face:
* Now if you know gain add it and if not leave it to 1
* Now press check button and wait for Result. Now there are few possibilities.

1. You will get desired value :blush:
2. You will get the desired value but need to add different gain. 
For example, you read frequency and you get a result value as 4998 so your gain value will be 0.01 so you will get a result as 49.98 :blush:
3. You will get random value but not we need it means now we have to try different data types selection for a correct response so try different data type and we are sure that one of the following data types will give you the correct response.:blush:
4. You will get CRC fail error it means that receiving packet from a slave is not ok and CRC is not valid. So there is a possibility of connection error.
5. You will get Timeout error.
 <a><img src="http://electrosoul.in/product_photo/RS485_Gateway_WiFi/10.jpeg" width="600"></a>
 ## How To  Debug TimeOut Error ?
 * Check that Slave ID is proper.
 * Change Function Code and try.
 * If above two do not give Result without Error. Then check your address value and try to decrement your address value by 1.
    
     
	        



