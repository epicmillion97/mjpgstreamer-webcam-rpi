# mjpgstreamer-webcam-rpi
Using mjpgstreamer on startup of raspberry pi as a webcam.  
This project relies on https://github.com/jacksonliam/mjpg-streamer which is the backbone of the project

## Installation of mjpeg-streamer
- `git clone https://github.com/jacksonliam/mjpg-streamer`
- `sudo apt-get install cmake libjpeg8-dev`
- `sudo apt-get install gcc g++`
- `cd mjpg-streamer-experimental`
- `make`
- `sudo make install`

## Testing the Program
Run this command to test the installation of mjpeg-streamer  
`./mjpg_streamer -o "output_http.so -w ./www" -i "input_raspicam.so"`  
  Open your browser to your raspberry pi's hostname or ip address followed by port 8080
   `http://raspberry.local:8080`

## Installing Auto startup
- `git clone https://github.com/epicmillion97/mjpgstreamer-webcam-rpi`
- `cd mjpgstreamer-webcam-rpi`
- `sudo mv ./mjpgcheck /usr/bin/mjpgcheck`
- `sudo chmod u+x /usr/bin/mjpgcheck`
- `crontab -e`
- Add the line of `@reboot sleep 20 && /usr/bin/mjpgcheck` to the end of crontab

## Setting up OBS to use webcam
- Get the hostname or IP address of the raspberry pi 
- Add a new Browser Capture to OBS 
- Edit the URL to be `http://raspberrypi.local:8080/javascript_simple.html` **MUST REPLACE `raspberrypi.local` to your hostname or IP**
