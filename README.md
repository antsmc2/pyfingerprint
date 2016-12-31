# Python library for ZFM-20 and R303A type fingerprint sensors

The PyFingerprint library allows to use fingerprint sensors following same protocol as the ZhianTec ZFM-20 and R303A fingerprint sensors.

**Note:** The library is inspired by the C++ library from Adafruit Industries:  
<https://github.com/adafruit/Adafruit-Fingerprint-Sensor-Library>


## Installation from source file

**Note:**  This has been tested on the following operating systems:
   1. This should work properly on Debian 7 (Wheezy), Debian 8 (Jessie), Ubuntu 14 (I pretty much expect it to work on any linux machine). 
   2. Windows OS (tested on windows 7 & windows 10 and it works)
   3. Mac OS X (tested on my Yosemite version 10.10.5. But pretty much to expect it to work on your mac)
**Note**: The library has been tested on ZFM-20 and R303A fingerprint sensors.

Clone this repository:

    ~$ git clone https://github.com/bastianraschke/pyfingerprint.git

Install library dependencies:

    ~$ cd ./pyfingerprint/src/
    ~$ pip install -r pip-requires.txt
    
Install pyfingerprint:

    ~$ python setup.py build
    ~$ python setup.py install    
    
On a linux machine, you may additionally choose to run the following commands to allow non-root user to use the serial port

    ~$ sudo usermod -a -G dialout $USER
    ~$ sudo reboot

## Alternative Installation (Debian)

**Note:** This should work properly on Debian 7 (Wheezy) and Debian 8 (Jessie).

### Package building

First install the packages for building:

    ~$ sudo apt-get install devscripts

Than clone this repository:

    ~$ git clone https://github.com/bastianraschke/pyfingerprint.git

Build the package:

    ~$ cd ./pyfingerprint/src/
    ~$ debuild

### Installation

Install the built Debian package:

    ~$ sudo dpkg -i ../python-fingerprint*.deb

Install missing dependencies:

    ~$ sudo apt-get -f install

Allow non-root user "pi" (replace it correctly) to use the serial port devices:

    ~$ sudo usermod -a -G dialout pi
    ~$ sudo reboot


## How to use the library

### Defining the fingerprint device location:

On a windows OS, pyfingerprint assumes this location to be "COM3", otherwise it assumes the location to be "/dev/ttyUSB0"

You can overwrite this behaviour by setting environment variable **FP_DEVICE_LOC**. Set **FP_DEVICE_LOC** to the
appropriate path where your device is connected. 

### Enroll a new finger

Navigate to source project folder, then:

    ~$ cd src/files/examples/
    ~$ python example_enroll.py

### Search an enrolled finger

Navigate to source project folder, then:

    ~$ cd src/files/examples/
    ~$ python example_search.py

### Delete an enrolled finger

Navigate to source project folder, then:

    ~$ cd src/files/examples/
    ~$ python example_delete.py

### Download image of a scanned finger

Navigate to source project folder, then:

    ~$ cd src/files/examples/
    ~$ python example_downloadimage.py

## Questions

If you have any questions to this project, just ask me via email:

<bastian.raschke@posteo.de>
