The bellman equation is used for finding the shortest path so the agent get less penalty for reaching to the goal .

for example 

`1  2  5  `

`3  4  6  `

- **The agent starts at state 1** and wants to reach **state 4**, which gives a reward of **+10**.
- Each move (up, down, left, right) costs **-1 penalty**, so the goal is to find the **shortest path** to reach **state 4** with the **least total penalty**.

### **Step-by-step (Intuition):**

1. **State 4** is the goal, so V(4)=10V(4) = 10V(4)=10.
    
2. The agent will calculate the value of neighboring states (like 1, 2, 3, 5, and 6) using the Bellman equation:
    
    - **For state 1:**  
        Possible actions are to move to state 2 or state 3. The agent compares both options to decide which leads to the goal with the highest value and the smallest penalty.
        
        Example:  
        V(1)=−1+0.9×max⁡(V(2),V(3))V(1) = -1 + 0.9 \times \max(V(2), V(3))V(1)=−1+0.9×max(V(2),V(3))  
        (The agent picks the action that leads to the state with the highest value.)
        
3. The agent repeats this process, updating the values until it finds the **optimal path**.
    

---

### **Optimal Path in This Case**

The shortest path from **state 1 to state 4** is:

- 1→3→41 → 3 → 41→3→4
- This path has only **two moves** (with a total penalty of **-2**) compared to other longer paths, like 1→2→5→6→41 → 2 → 5 → 6 → 41→2→5→6→4, which would have a higher penalty.