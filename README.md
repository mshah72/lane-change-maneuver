# Implementation of Blame Free Lane Change Maneuver Algorithm using SUMO simulator

This project simulates autonomous vehicle (AV) behavior in a traffic environment using SUMO (Simulation of Urban MObility) and the Traffic Control Interface (TraCI). The core focus is on implementing a lane change maneuver algorithm for AVs based on real-time traffic conditions.

### Overview

The simulation environment in SUMO is set up with a predefined road network. AVs are loaded into the simulation, each controlled through a Python script that interacts with the SUMO environment via TraCI. The script manages each AV's decisions on when and how to change lanes safely and efficiently.

### Steps in Lane Change Maneuver

#### 1. Initialize Simulation
```
- Start SUMO Simulation: Launches the SUMO environment with TraCI support.
- Connect to TraCI Server: Establishes a connection between the Python script and TraCI to control AVs in the simulation.
```

#### 2. Load Vehicles
```
- Add AVs: Insert autonomous vehicles into the simulation with predefined routes and characteristics.
- Set Initial Parameters: Defines initial speeds and speed limits for each AV.
```

#### 3. Main Simulation Loop
```
- Simulation Steps: The simulation progresses in discrete time steps.
- Data Retrieval: At each step, the script retrieves data about each AV's position, speed, and surrounding traffic conditions using TraCI commands.
```

#### 4. Execute Lane Management Algorithm
```
- Monitor Traffic Conditions: Collects real-time data about vehicle positions, speeds, and nearby vehicles.
- Lane Change Decisions:
  - Safety Distance Calculations: Determines safe following distances (`dCrash` and `dResponse`) based on AV's speed and braking capabilities.
  - Assess Lane Availability: Checks for the presence of other vehicles (blockers and non-blockers) adjacent to the AV using `check_blockers_and_non_blockers`.
  - Evaluate Lane Change: Considers changing lanes if it is safe and beneficial based on traffic conditions and safety distances.
- Apply Decisions: Adjust the AV's speed or change lanes as decided by the algorithm.
```

#### 5. Update Vehicle States
```markdown
- Send Commands to AVs: Updates the SUMO simulation with new speed or lane change commands for each AV.
- Continue Simulation: Advances the simulation to the next step.
```

#### 6. Monitoring and Data Collection
```markdown
- Data Logging: Collects data on vehicle behaviors, traffic flow, and lane change incidents throughout the simulation.
- Performance Analysis: Monitors AV performance in terms of safety and traffic efficiency.
```

#### 7. Close Simulation
```markdown
- Terminate Connection: Gracefully closes the TraCI connection once the simulation is complete.
- Data Analysis: Reviews the collected data to assess the effectiveness of the lane change algorithm.
```

### Conclusion

This simulation project provides insights into how AVs can make real-time lane change decisions in a dynamic traffic environment. The algorithm prioritizes safety while maintaining traffic flow efficiency, showcasing the potential of autonomous vehicles in urban mobility.

---

## How to install SUMO and run the script

### SUMO Installation

**Windows:**
1. Download the SUMO binaries from [SUMO's official website](https://sumo.dlr.de/docs/Downloads.php#windows).
2. Follow the installation instructions provided in the download package.

**Ubuntu:**
1. Open a terminal and run the following commands:
   
   ```
   sudo add-apt-repository ppa:sumo/stable
   sudo apt-get update
   sudo apt-get install sumo sumo-tools sumo-doc
   ```
   For more details, visit the [SUMO Installation Guide for Ubuntu](https://sumo.dlr.de/docs/Installing/Linux_Build.html).

**MacOS:**
1. Install Homebrew if it's not already installed, using the following command:
   
   ```
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
   ```
2. Install SUMO using Homebrew:
   
   ```
   brew tap dlr-ts/sumo
   brew install sumo
   ```
   Refer to the [SUMO Installation Guide for MacOS](https://sumo.dlr.de/docs/Installing/MacOS_Build.html) for detailed instructions.

**Docker:**
1. Ensure Docker is installed on your system. If not, install it from the [official Docker website](https://www.docker.com/get-started).
2. Run SUMO on Docker using the following command:
   
   ```
   docker pull dlrts/sumo
   docker run -it dlrts/sumo
   ```
   For more details, check the [SUMO Docker Hub page](https://hub.docker.com/r/dlrts/sumo).

---

## Usage

### Step 1 - Create a map with traffic using OSMapWizard

To create a map using OSMapWizard in SUMO, follow these steps:
1. Navigate to `sumo/tools/osmWebWizard.py`.
2. Specify the area for which you want the map.
3. Adjust the settings as per your requirements and generate the map.

For detailed instructions, refer to the [OSMapWizard documentation](https://sumo.dlr.de/docs/Networks/Import/OpenStreetMap.html).

### Step 2 - Run the simulation by executing the Python script written using the TraCI library available in SUMO 

1. Edit the location sumoconfig file. 
2. Execute the Python notebook file `lane-change-maneuver.ipynb`.
3. Open the `.csv` file generated at the end of the simulation to see the data related to the vehicles.

---

## References

1. [TraCI Library Documentation](https://sumo.dlr.de/docs/TraCI.html)
