# Hénon-Heiles System Simulation

This script models and analyzes the dynamics of the Hénon-Heiles system, a fundamental example in Hamiltonian mechanics that explores the transition between regular and chaotic behavior. The system is simulated using Python with numerical integration and visualization of its dynamics.

---

## Features

1. **Numerical Integration**: 
   - The differential equations derived from the Hénon-Heiles Hamiltonian are solved using the `solve_ivp` function from the SciPy library.

2. **Visualization**:
   - **Phase Space Trajectory**: Plots the particle's trajectory in the \(x\)-\(y\) plane.
   - **Poincaré Section**: Visualizes intersections of trajectories with the plane \(y = 0\) to study the system's dynamics.

3. **Parameter Configuration**:
   - Easily modify initial conditions, integration time, and visualization options.

---

## How It Works

1. **Hénon-Heiles Equations**:
   The Hamiltonian for the system is:
   \[
   H = \frac{1}{2}(p_x^2 + p_y^2) + \frac{1}{2}(x^2 + y^2) + x^2y - \frac{y^3}{3},
   \]
   which describes the total energy of the system. The equations of motion derived from this Hamiltonian are:
   \[
   \dot{x} = p_x, \quad \dot{y} = p_y,
   \]
   \[
   \dot{p}_x = -x - 2xy, \quad \dot{p}_y = -y - x^2 + y^2.
   \]

2. **Numerical Solution**:
   The equations are solved using the Runge-Kutta method (`RK45`) over a time span of \(t = [0, 1500]\), evaluated at 5000 points.

3. **Initial Conditions**:
   The initial conditions are:
   \[
   z_0 = [x_0, y_0, p_{x0}, p_{y0}] = [0.2, 0.0, 0.0, 0.3].
   \]
   These were chosen to ensure the system evolves within an energy range exhibiting regular trajectories. This enables the identification of periodic and quasi-periodic behavior in the system's dynamics.

---

## Requirements

- Python 3.x
- NumPy
- SciPy
- Matplotlib

Install the required libraries via pip:
```bash
pip install numpy scipy matplotlib
```
## Notes:

### Quasi-periodic dynamics.
- Modifying the initial conditions allows for exploration of different dynamic regimes, including chaos.

### Customization:
- To explore different behaviors, update the following parameters in the script:
z0: [x0, y0, px0, py0] -> Initial conditions for position and momentum.
t_span: [t_start, t_end] -> Time interval for the simulation.
atol: Adjust the tolerance in the poincare_section() function for more accurate or broader filtering.

### Output:
- The script generates two output plots:
* phase_space.png: Visualizes the trajectory in the phase space (x vs. y).
* poincare_section.png: Displays the Poincaré section at y = 0.
- Both files are saved in the working directory.

