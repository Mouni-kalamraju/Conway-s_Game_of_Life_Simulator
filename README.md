# Conway-s_Game_of_Life_Simulator

A highly optimized and interactive Python implementation of Conway's classic cellular automaton, the Game of Life. This simulator utilizes NumPy for fast, vectorized grid updates and Matplotlib for real-time visualization. It features an interactive setup mode and robust automatic termination checks.

## ✨ Key Features

  * **Fast Simulation:** Utilizes **NumPy's vectorized operations** (`np.roll`) for highly efficient calculation of the next generation, especially on large grids.
  * **Dynamic Configuration:** Grid size and maximum iteration limits are set by the user at **runtime**.
  * **Toroidal Boundary Conditions:** The grid wraps around, meaning cells on the edges interact with cells on the opposite side of the board.
  * **Interactive Setup:** Users can choose between a random initial state or manually **"draw" the configuration** by clicking cells on the plot interface.
  * **Automatic Termination:** The simulation intelligently stops if any of the following conditions are met:
      * **Extinction:** All live cells die.
      * **Loop Detection:** The grid state returns to a previous state (indicating a still life or an oscillator).
      * **Max Iterations:** A configurable hard limit is reached.
  * **Clean Visualization:** Real-time generation count and status messages (**Running/Terminated**) are dynamically displayed in the plot title.

## Tools and Libraries

This project is built entirely in Python and utilizes the following libraries:

| Category | Library | Purpose | Installation |
| :--- | :--- | :--- | :--- |
| **Numerical Operations** | `numpy` | High-performance array and vectorized operations for efficient generation calculations. | `pip install numpy` |
| **Visualization/Interaction** | `matplotlib` | Real-time plotting, animation (`FuncAnimation`), and interactive user input handling. | `pip install matplotlib` |

## 📦 Installation

1.  **Clone the repository:**

    ```bash
    git clone [https://github.com/Mouni-kalamraju/Conway-s_Game_of_Life_Simulator.git](https://github.com/Mouni-kalamraju/Conway-s_Game_of_Life_Simulator.git)
    cd Conway-s_Game_of_Life_Simulator
    ```

2.  **Install dependencies:**

    ```bash
    pip install numpy matplotlib
    ```

## 🚀 How to Run

Execute the Python script from your terminal:

```bash
python Conway_Game_of_Life_simulator.py
```

### Runtime Configuration

When you run the script, you will be prompted in the console to configure the simulation parameters:

1.  **Enter Grid Size:** Define the dimension of the square grid (e.g., `50`).
2.  **Enter Max Iterations:** Set the maximum number of generations before the simulation forces a stop (e.g., `100`).
3.  **Choose Mode:** Select the starting state:
      * **User Setup (`U`):** The plot opens with a blank grid for interactive drawing.
      * **Random Start (`R`):** The simulation starts immediately with a randomized population.

### Interactive Controls (User Setup Mode)

If you select **User Setup** (`U`), use the following controls:

| Key/Action | Description |
| :--- | :--- |
| **Mouse Click** | **Toggles the state of a cell** (Dead ↔ Live). |
| **Grid Lines** | Thin gray lines help you precisely identify and click individual cells. |
| **Press 'S' Key** | **Starts the simulation.** The animation begins running the Game of Life rules. |

## 🧬 Game Rules and Termination

The simulation follows the standard four rules of Conway's Game of Life:

1.  **Underpopulation:** Any live cell with fewer than two live neighbors dies.
2.  **Survival:** Any live cell with two or three live neighbors lives on to the next generation.
3.  **Overpopulation:** Any live cell with more than three live neighbors dies.
4.  **Reproduction:** Any dead cell with exactly three live neighbors becomes a live cell.
