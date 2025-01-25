# Micro-ROS research notes
Micro ROS is a framework / SDK for building ROS nodes that can run on ESP32, RP2040, or STM32 micro controllers. Ideally this would assist with development by allowing development and testing of ROS nodes on cheap micro controllers.

## Articulated Robotics yt tutorial
[Link to the video](https://www.youtube.com/watch?v=MBKAZ_2P1Sk) watched. In this video the following is shown:
1. Brief explaination of what uROS is
2. Setting up an SDK for pico
	- adding development layers to a project
	- building micro-ROS from cloned repo
3. Flashing to pico using pico-tool
4. Using a docker container for the micro-ROS agent, 6:48
5. Interacting with micro-controller running a Node
6. Hardware config
7. Customising the code
	- ading c++ compatibility
	- Explaining how to create a new publisher
	- Highlights how the spin works
8. Customising code adding subscriber
	- adding a new library
		- CMake build modification
	- adding subscription to the executor
9. Uses another ros2 Node to interact and change the button color
10. Creating a service
	- Setting the service up in ROS
	- building additional packages demonstrated
		- there is a difference between pico SDK and other approaches due to precompiled workspace
		- Uses another docker container
	- Adding service in the code
		- Request and response
	- Messages need memory allocated
11. Running the ROS nodes
	- Flashes the pico
	- Running demonstrating the command line usage to control the node via the service.

Notes:
- micro-ROS Agent needed to communicate with uROS on micros
	- This tutorial demonstrated using a docker image
- When changing executor be sure to update the number of topics that can be handled
- Dynamic memory allocation can be difficult, this is required for joint states.
- Defining a service is very simple
