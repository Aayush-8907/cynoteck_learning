The agent is learning from **what it actually does** in the environment, so the policy **remains tied** to the actions it takes in each state.

### **On-Policy Learning Example**:

1. The agent (car) learns the policy that says: "When it's time to park, go left and park in a certain way."
2. The agent performs the action (go left, park) based on this **current policy**.
3. After the first day of parking the car, the agent **updates its knowledge** based on the actions it took (e.g., parking the car in a forward direction). This policy is updated based on its actual experience (what it did).
4. **The next day**, when the agent parks, it will follow the same policy, using the knowledge it gained from previous actions.
    - So, if it parked the car forward yesterday, it will park the car **forward again** today because the policy was learned from its past experience, and it updates based on its past actions.