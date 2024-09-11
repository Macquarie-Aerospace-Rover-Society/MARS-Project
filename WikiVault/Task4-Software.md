# Task 4 breakdown 
High level breakdown of Task 4 from the perspective of software.

## Mission control
For this task a large amount of data processing is required
- Log all data
  - Have software set up to process incoming data.

### Autonomous mode failure
If autonomous mode fails, human pilots must be able to take over to guide the robot to areas that need scanning. This requirement implies that we could test autonomous mapping by disconnecting the robots Guidance system from its drive system and placing a human in the middle to sanity check. This would also help build human intuition about the robots limits, and blind spots.

## Robot state Activity 4
We believe that software can be changed between tasks, as a result I am ignoring all other tasks and only considering Task 4.

In addtion it is required that no prior knowledge be used on this task, so we must be able to prove that to be the case if asked.

#### Sensor Data needed
- Visual.
  - Zoom lens?
- Trajectory.
  - Encoders on the motors.
- Positional.
  - Magnetic compas
  - Gyroscope
  - Accelerometer
- Pre-processed mappings of sensor data to navigation difficulty.

### Activity 1
Leave the starting square
- Detect the square.
  - Visual data processing
- Plot a course out of the square.
  - If no square detected, pick any direction and assume vision is compromised.
- Send control signals to drive system.
- Begin Data stream to mission control.

#### Expected resources needed
Basic
- Fault tolerant since fallback to blind movement possible.

### Activity 2
Autonomous movement to points, at the end of visiting points should also plan to explore unvisited areas.
- Be able to accept some form of basic map
  - Extend: Be able to add new landmarks to the map, and gauge location based off landmarks
- Guidance system has to be able to plot over terrain.
  - SLAAM, may be useful to determine navigability.
- Computer vision is needed to scan the landmark
  - Unless certain the landmark has been scanned successfully, image it from all sides.
    - Images need to be resolvable. Potential need for zoom lens
- Anomaly detection
  - If an anomaly is detected scan it and enter the state for activity 3.


#### Expected resources needed
Intermediate
- With provided map approximate location could be calculated with basic Trajectory plotting.

### Activity 3
This activity state should be devoted to detection / identification of anomalies.
- This state should be able to schedule a visit to an area of interest for closer examination.
- As part of this activity anomaly should be extended to include poorly mapped areas of the arena. 


### Activity 4
Presentation
- Data processing software is needed
- rendering software is needed
- Powerpoint is needed

Human proceedures should be considered as part fo the system for this activity. Training will be required, and user manuals for new software are needed.