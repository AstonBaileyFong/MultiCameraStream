# MultiCameraStream
MVVM Structure
1. Model
* CameraModel Abstract Class
  * Specifies what attributes a camera object can have
* GoProModel Class
  * Child class of the CameraModel abstract class
  * Specifies any specific attributes that GoPro cameras possess from the perspective of the program.


2. View
* MainActivity
  * Display options for connecting one or more cameras
  * Connects required amount of cameras and displays the live feed on the screen.
  * Has options for recording sections of playback 


3. ViewModel
* GoProBlueToothViewModel
  * Child class of the GoProModel class
  * Contains functions for connection and interaction with the camera via bluetooth
* GoProWiFiViewModel
  * Child class of the GoProModel class
  * Contains functions for connection and interaction with the camera via wifi (a bluetooth connection is required beforehand
* MainViewModel
  * Establishes protocols and orders for how to connect to specific camera models.
  * For GoPros, establishes a bluetooth connection with the required camera in question, before establishing a wi-fi connection
  * Communicates user instructions to the various cameras (i.e. record, stop, save)
