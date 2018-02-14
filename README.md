# Remote streaming live video
This an implementation on how to get a remote live video streaming connection between 2 different processes using websockets. The video image is captured through [OpenCV](https://opencv.org/) on one machine and video is served in another machine. This approach serves best the scenario where the Webserver is located in a different network than the machine that is producing the video streaming.

The streaming process can be summed into the following steps:
1. Capturing video image
2. For each frame, serialize the image
3. Flush the data to the Webserver listening socket
4. Deserialize the data into a jpeg image
5. Serve the result in the web page

The web framkework used for the webserver is [Flask](http://flask.pocoo.org/).

## Installation
This example runs with Python. Also install the following Python dependencies (pip makes it dead simple):
* opencv-python
* flask