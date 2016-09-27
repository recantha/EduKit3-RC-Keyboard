## Please consider these instructions a BETA until they are absorbed and reformatted into the EduKit 3 worksheets.

# Remote control for CamJam EduKit 3 using SSH and a keyboard

What you’ll need:
* An extra computer with SSH capabilities (see https://www.raspberrypi.org/documentation/remote-access/ssh/ for SSH options for all different kinds of platforms)
* Some way, on the computer, to issue keystrokes (i.e. a keyboard or a touchscreen with a virtual keyboard)
* A wi-fi dongle for the Raspberry Pi.
* Some way of determining your Pi’s IP address (see below).

## Wi-Fi
What we will do is to use a modified EduKit script that will read in keystrokes and convert them into commands to drive the motors.

First of all, boot up your Raspberry Pi to desktop mode. Then, follow these instructions for connecting to your wi-fi network:

`https://www.raspberrypi.org/documentation/configuration/wireless/`

Next, you will need some way of determining the IP address of your Pi. If your Pi is plugged into a monitor, this is easy - hover your mouse over the wifi connection icon and make a note of the address (e.g. 192.168.1.69).
Alternatively, open up a Terminal session and type ‘ifconfig’ and make a note of the IP address of the wlan0 connection.

Once you are headless (i.e. not connected to a monitor), this IP address might change when you reboot. There are a few ways of determining the IP address of a headless Pi. For example:
* Login to your wi-fi router and use the in-built functions to see IP addresses of your connected devices.
* Have the Raspberry Pi email you with the IP address. A script to do this can be found here: `https://gist.github.com/binaryghost/4269368` This script can be integrated with your robot script as it is written in Python.

## Connect and install
Now that you know your Pi’s IP address, switch to your other computer.
Open up your SSH client software and connect to the Pi’s IP address using the username pi and password raspberry.

Next, you’re going to install the software to take in keystrokes and run the motors.
Do the following inside the SSH session:
`git clone https://github.com/recantha/EduKit3-RC-Keyboard`

If git reports an error and gives you instructions to set-up a username and name, please follow the instructions given.

## Running the script, controlling the robot
Go into that folder:
`cd EduKit3-RC-Keyboard`

Run the script:
`python rc_keyboard.py`

The following keystrokes can be used:
* W - forward
* S - backward
* A - left
* D - right
* Q - quit
 
