# MultiCameraStream
MVVM Structure
1. Model

The Model of this program is the cameras the program will be interacting with. For this, we must define what a camera is by defining it's attributes.
* CameraModel Abstract Class
  * Specifies what attributes a camera object can have
* GoProModel Class
  * Child class of the CameraModel abstract class
  * Specifies any specific attributes that GoPro cameras possess from the perspective of the program.


2. View

The View of this program is the user interface, which dictates how the user can interact with the program.
* MainActivity
  * Display options for connecting one or more cameras
  * Connects required amount of cameras and displays the live feed on the screen.
  * Has options for recording sections of playback 


3. ViewModel

The ViewModel of this program is the means by which the program itself communicates with the cameras. This involves outlining the methods of communication (i.e. bluetooth/wi-fi) to the cameras, and establishing protocols for connection and communication.
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
