### **Step 1: Modifying the Grid**
- **Double Click/Single Click** on any cell in the grid to change its state. 
  - **Terminal States:** These are your target or end points (like a charging station). 
  - **Blocked States:** These are obstacles or no-go areas.

### **Step 2: Adjusting Settings**
- Use the **Control Menu** to change grid size and algorithm parameters.
  - Adjust things like grid dimensions or algorithm settings to see how they affect the outcome.

### **Step 3: Understanding the Grid**
- The grid shows the **State Value Function** for each cell.
  - Each cell's value represents the expected reward for moving in the directions: Left, Up, Right, Down.

### **Step 4: Iteration and Sub-Iterations**
- Click **"Next Value"** to progress through the current iteration step-by-step.
  - The **Sub-Iterations** count increases with each step.
  - When a terminal state or the maximum steps per iteration are reached, the iteration count increases and the steps reset to 0.

### **Step 5: Moving to the Next Iteration**
- Click **"Next Iteration"** to proceed to the next cycle of the algorithm.
  - This allows you to see how the algorithm refines its strategy over time.

### **Step 6: Learning the Policy**
- The **Arrows in the Left Grid** indicate the currently learned policy.
  - These arrows guide you towards the most rewarding actions in each state.

### **Step 7: Reaching the Optimal Policy**
- When the State Value Functions of all cells stabilize, an **Optimal Policy** is achieved.
  - A message will be displayed indicating that the best strategy has been found.
