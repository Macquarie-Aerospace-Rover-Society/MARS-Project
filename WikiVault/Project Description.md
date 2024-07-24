
# Overview

```mermaid
stateDiagram 
	state Rover{
		Mech : Mechanical
		Elec : Electrical
		Comp : Software
	}

	state MissionControl {
		Tele : Antenna
		Terminal : Control consoles
		GUI : User interface
	}
	MissionControl --> Rover : Commands
	Rover --> MissionControl : Mission Data
class  internal-link;
```
