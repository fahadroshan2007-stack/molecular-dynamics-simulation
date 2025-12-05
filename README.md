# 3D Molecular Dynamics Simulation in Python

This project simulates the motion of multiple interacting particles confined in a 3D box using a simple molecular dynamics model and visualizes their trajectories in real time. [file:21]

## Features
- Simulates 13 particles in a cubic box with elastic reflections at the boundaries. [file:21]
- Initializes particle positions and velocities randomly within the box volume. [file:21]
- Computes pairwise forces between particles and accumulates accelerations at each time step. [file:21]
- Uses a velocity-Verlet–style time integration scheme with configurable time step `dt` and total steps `T`. [file:21]
- Renders a 3D scene using VPython with colored spheres, trails, coordinate axes, and box edges. [file:21]
- Tracks and stores the total kinetic energy of the system over the course of the simulation and plots it using VPython. [file:21]

## Tech Stack
- **Language**: Python
- **Libraries**:
  - NumPy – vector and matrix operations for positions, velocities, and forces. [file:21]
  - VPython – real-time 3D visualization of particles and box. [file:21]
  - Matplotlib – plotting the total kinetic energy vs. simulation time. [file:21]

## How It Works

### 1. Initialization
- Defines the number of particles `N`, box size `L`, time step `dt`, and total steps `T`. [file:21]
- Randomly initializes particle positions inside the cube and assigns random velocities in 3D. [file:21]
- Sets up VPython objects: 3D canvas, axes arrows, corner edges of the box, and colored spheres with trails for each particle. [file:21]

### 2. Force Calculation
- For each pair of particles, computes the distance vector and its magnitude. [file:21]
- Applies a simple pairwise interaction model (repulsive/attractive depending on distance) and accumulates the resulting acceleration on each particle. [file:21]

### 3. Time Integration and Boundary Handling
- Updates velocities and positions using a velocity-Verlet–style scheme: half-step velocity update, position update, then full velocity update after new accelerations. [file:21]
- Enforces box boundaries by reflecting particles at ±L/2 along each axis and inverting the corresponding velocity component. [file:21]

### 4. Energy Tracking and Visualization
- Computes kinetic energy of each particle from its velocity and sums to get total system kinetic energy at regular intervals. [file:21]
- Stores kinetic-energy values in a history array. [file:21]
- After the simulation, uses matplotlib to plot total kinetic energy vs. time steps. [file:21]
- VPython window shows the real-time motion of particles and their trails throughout the run. [file:21]

## File Structure
- `molecular_dynamics_vpython.py` – main simulation script containing:
  - Parameter setup (N, L, dt, T). [file:21]
  - Force calculation, reflection, energy functions. [file:21]
  - VPython visualization setup. [file:21]
  - Simulation loop and kinetic-energy plotting. [file:21]

## Requirements
- Python 3.x
- Recommended to use a virtual environment.

### Install Dependencies

## How to Run
1. Clone or download this repository.
2. Ensure dependencies are installed.
3. Run the script from the project directory:
4. A VPython window will open showing the 3D particle motion inside the box. [file:21]
5. After the simulation completes, a matplotlib window will display the total kinetic energy vs. time steps. [file:21]

## Possible Extensions
- Replace the simple force model with a more realistic potential (e.g., Lennard-Jones).
- Add temperature control or a thermostat model.
- Compute and plot additional observables (pressure, radial distribution function, etc.).
- Add UI controls (sliders, buttons) to adjust parameters like number of particles or box size. [file:21]
