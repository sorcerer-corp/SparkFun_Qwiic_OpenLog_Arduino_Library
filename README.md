SparkFun Qwiic OpenLog Library
===========================================================

[![SparkFun Qwiic OpenLog](https://cdn.sparkfun.com/assets/parts/1/3/5/5/4/15164-SparkFun_Qwiic_OpenLog-01.jpg)](https://www.sparkfun.com/products/15164)


[*SparkFun Qwiic OpenLog (DEV-15164)*](https://www.sparkfun.com/products/15164)


This library makes using the Qwiic OpenLog easy to use. It creates a Print class so that you can do things like

    mylogger.print("The battery voltage is:");
    mylogger.println(batteryVoltage);

And your data will be recorded to LOG00001.TXT for later review. Please see the examples to get started.

Available commands:

* boolean **begin**(int deviceAddress) - Start comminication with a given OpenLog
* String **getVersion**() - Returns a string that is the current firmware version
* uint8_t **getStatus**() - Returns various status bits
* boolean **setI2CAddress**(uint8_t addr) - Set the I2C address of the OpenLog
* boolean **append**(String fileName) - Open and append to a file
* boolean **create**(String fileName) - Create a file but don't open it for writing
* boolean **makeDirectory**(String directoryName) - Create the given directory
* boolean **changeDirectory**(String directoryName) - Change to the given directory
* int32_t **size**(String fileName) - Given a file name, read the size of the file
* void **read**(uint8_t* userBuffer, uint16_t bufferSize, String fileName) - Read the contents of a file into the provided buffer
* boolean **searchDirectory**(String options) - Search the current directory for a given wildcard
* String **getNextDirectoryItem**() - Return the next file or directory from the search
* uint32_t **remove**(String thingToDelete) - Remove file or directory including the contents of the directory

The SparkFun Qwiic OpenLog is the smarter and better looking cousin to the extremely popular [OpenLog](https://www.sparkfun.com/products/13712). We've ported the serial based interface to I2C. Now you can daisy chain lots of I2C devices and log them all without taking up your serial port.

We've written a large number of example sketches to show how to record logs, create new logs, create and navigate directories, remove files and directories, and read the contents of files. 

Qwiic OpenLog supports clock stretching which means it performs even better than the original! Qwiic OpenLog will record data up to 21,000 bytes per second at 400kHz. As the receive buffer fills up QOL will hold the clock line letting the master know that it is busy. Once QOL is finished with a task it releases the clock allowing the data to continue flowing without corruption.

Need to get freaky and have multiple data loggers on the same bus? You're in luck. Qwiic OpenLog has both a solder jumper to allow for two devices on the same bus as well as a software setting to allow for the setting of any I2C address. Don't get too freaky though; the limit is 111 devices (0x08 to 0x77) on the same bus. Any microSD card up to 32GB will work.

We will be adding more features to the firmware over time and we've made it very easy to upgrade! If you're comfortable sending a sketch to an Uno then you can upgrade the firmware on Qwiic OpenLog.

Library written by Nathan Seidle ([SparkFun](http://www.sparkfun.com)).

Repository Contents
-------------------

* **/examples** - Example sketches for the library (.ino). Run these from the Arduino IDE. 
* **/src** - Source files for the library (.cpp, .h).
* **keywords.txt** - Keywords from this library that will be highlighted in the Arduino IDE. 
* **library.properties** - General library properties for the Arduino package manager. 

Documentation
--------------

* **[Installing an Arduino Library Guide](https://learn.sparkfun.com/tutorials/installing-an-arduino-library)** - Basic information on how to install an Arduino library.
* **[Hookup Guide](https://learn.sparkfun.com/tutorials/qwiic-openlog-hookup-guide)** - Basic information on how to install an Arduino library.
* **[Product Repository](https://github.com/sparkfun/Qwiic_OpenLog)** - Main repository (including hardware files)

License Information
-------------------

This product is _**open source**_! 

Various bits of the code have different licenses applied. Anything SparkFun wrote is beerware; if you see me (or any other SparkFun employee) at the local, and you've found our code helpful, please buy us a round!

Please use, reuse, and modify these files as you see fit. Please maintain attribution to SparkFun Electronics and release any derivative under the same license.

Distributed as-is; no warranty is given.

- Your friends at SparkFun.
