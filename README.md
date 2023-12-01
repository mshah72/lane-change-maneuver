# Implementation of Blame Free Lane Change Maneuver Algorithm using SUMO simulator

*****Project Description

---

## Installation

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
2. Execute the Python notebook file `blaft.ipynb`.
3. Open the `.csv` file generated at the end of the simulation to see the data related to the vehicles.

---

## References

1. [TraCI Library Documentation](https://sumo.dlr.de/docs/TraCI.html)