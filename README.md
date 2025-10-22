# Stewart Platform Course Project

## Overview
This repository hosts the code and documentation for a six-degree-of-freedom Stewart Platform that was developed as part of the FRTN85 course project (Group 6). The aim of the project is to design, build, and control a parallel robot that can manipulate a payload with high precision by coordinating six linear actuators. The repository is organised to keep the embedded firmware, host-side tooling, and project documentation in one place so that the platform can be rebuilt or extended by future contributors.

## Repository Structure
- `arduino/` – Source files for the embedded firmware that runs on the microcontroller controlling the actuators. Add Arduino sketches (`.ino` files) and supporting libraries here.
- `docs/` – Project documentation, including design notes, kinematic derivations, wiring diagrams, and reports.
- `scripts/` – Host-side helper scripts for calibration, data logging, or simulation.

Each directory currently contains a placeholder file (`.gitkeep`) so that the folder is tracked even when empty. Replace the placeholders as you begin to populate the repository with real content.

## Getting Started
1. **Clone the repository**
   ```bash
   git clone https://github.com/<your-organisation>/stewart-platform.git
   cd stewart-platform
   ```
2. **Install the required tools**
   - [Arduino IDE](https://www.arduino.cc/en/software) (or [Arduino CLI](https://arduino.github.io/arduino-cli/latest/)) for compiling and uploading firmware to the microcontroller.
   - Python 3.9 or newer if you plan to run any host-side scripts (virtual environments are recommended).

## Running the Platform
### 1. Build and Upload the Firmware
Once firmware sketches are added under `arduino/`, open the relevant `.ino` project in the Arduino IDE (or use the Arduino CLI):
```bash
arduino-cli compile --fqbn <board-fqbn> arduino/<sketch-folder>
arduino-cli upload --port <serial-port> --fqbn <board-fqbn> arduino/<sketch-folder>
```
Replace `<board-fqbn>` with the fully qualified board name (for example, `arduino:avr:uno`) and `<serial-port>` with the serial device that your board exposes when connected via USB.

### 2. Run Host-Side Scripts
When Python scripts are added to `scripts/`, install their dependencies (commonly recorded in a `requirements.txt`) and execute them from the project root:
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r scripts/requirements.txt
python scripts/<script-name>.py
```
These scripts can be used for calibration routines, kinematic solvers, or to send commands to the platform via serial communication.

### 3. Consult the Documentation
The `docs/` directory is the canonical location for build instructions, mathematical derivations, and troubleshooting guides. Add diagrams, bills of materials, and testing procedures here so that collaborators can reproduce the hardware setup and experiments.

## Contributing
1. Create a branch for your feature or fix.
2. Commit your changes with descriptive messages.
3. Open a pull request describing what has been added or changed and how it was tested.

Please keep documentation up to date as you implement new features or alter the mechanical/electrical design.

## License
Add the appropriate license for the project (for example, MIT, GPL, or a university-specific license) once it has been decided by the team.
