# Granovetter Threshold Simulation (participation_grid.ipynb)

This script implements a 2D Cellular Automata simulation of Mark Granovetter’s 1978 "Threshold Model of Collective Behavior." It is designed to visualize the tipping points where individual local decisions aggregate into a system-wide cascade (regime change).

### 1. The Logic

The simulation uses a **Moore Neighborhood** (8 neighbors) on a square grid. Each cell represents an agent with a threshold :

* ** (Instigators):** Agents who activate at  regardless of their surroundings.
* **:** Agents who activate only if  neighbors are already active.

The model is highly sensitive to the spatial distribution of  agents. A small cluster of instigators can "bridge" gaps between cautious agents, triggering a non-linear participation jump.

### 2. Implementation Details

The code is written in Python 3 and utilizes a vectorized approach for state updates:

* **Grid Initialization:** Total cells are determined by `grid_size` ().
* **Threshold Assignment:** Low thresholds () are assigned via user-defined counts. Remaining cells are populated with higher thresholds () to act as "damping" factors in the system.
* **Convergence:** The simulation runs iteratively until the system reaches a steady state (no further agents change state).

### 3. User Interface

The notebook includes an `ipywidgets` dashboard for real-time sensitivity analysis:

* **Sliders (T=0 to T=3):** Manually adjust the density of the most volatile agents.
* **Seed:** Controls the random spatial layout. Useful for testing how the same population density can lead to either total stasis or total revolution based purely on proximity.
* **Plotting:** Generates a `.png` heatmap where:
* **Navy Cells:** Active participants ().
* **Text Labels:** The individual threshold  of each cell.
* **White Labels:** Active agents.
* **Black Labels:** Inactive agents.



### 4. Dependencies

* `numpy` (Numerical arrays)
* `matplotlib` (Grid visualization)
* `ipywidgets` (Interactive dashboard)

### 5. Running the Simulation

Execute the cells in `participation_grid.ipynb`. Adjust the  slider to observe the "Phase Transition"—the point where a single additional instigator causes a marginal participation increase to become a total system flip.
