# AI for Engineers: Intro to Intelligent Agents

A hands-on educational lab introducing the fundamentals of intelligent agent design through a simulated robotic vacuum cleaner.

## 📖 Overview

This project teaches core AI and robotics concepts by building a **simple reflex agent**—a robot that perceives its environment through sensors and acts on it through actuators. Students will explore how agents make decisions, handle uncertainty, and work within resource constraints.

### The Scenario
You are an engineer building a robotic vacuum cleaner for a hallway with multiple rooms. Some rooms are clean, some are dirty. Your robot must:
- **Sense** the current room status (dirty or clean)
- **Decide** what action to take based on simple rules
- **Act** by cleaning or moving to the next room

## 🎯 Learning Objectives

By completing this lab, you will understand:

- **What is an Agent?** How sensors and actuators enable an agent to perceive and act
- **Reflex Agents** Simple rule-based decision making
- **Deterministic vs. Stochastic Environments** How uncertainty affects agent behavior
- **Resource Constraints** Real-world limitations like battery life
- **Probability & Randomness** Simulating noisy, unreliable sensors
- **Engineering Trade-offs** Balancing efficiency vs. robustness

## 📂 Project Structure

The lab is organized into progressive sections:

### Part 1: Setting up the Environment
- Represent a hallway as a Python list
- Use `1` for dirty rooms, `0` for clean rooms
- Understand why numerical representations are useful for computation

### Part 2: Building the Agent's "Brain"
- Implement `robot_brain()` function with simple IF-THEN rules
- Rule 1: If dirty → CLEAN
- Rule 2: If clean → MOVE_RIGHT
- Explore what happens with different rule sets

### Part 3: Running the Simulation
- Use a `while` loop to simulate the passage of time
- Implement the sense-decide-act cycle
- Watch the robot clean the entire hallway

### Optional Challenge 1: The Resource-Constrained Agent
- Add a `battery` variable (starts at 6)
- Cleaning costs 2 battery
- Moving costs 1 battery
- Robot stops when battery reaches 0 or hallway is clean
- Explore efficiency vs. effectiveness trade-offs

### Optional Challenge 2: The Noisy Sensor (Stochastic Environment)
- Simulate a faulty sensor with only 80% accuracy
- Sensor returns `'UNKNOWN'` 20% of the time
- Implement robust decision-making under uncertainty
- Run diagnostics to verify sensor probability (should fail ~20% of the time)
- Decide: conservative strategy (always clean on unknown) or efficient strategy (always move)?

## 🚀 How to Run

1. **Open the Jupyter Notebook:**
   ```bash
   jupyter notebook "Intelligent_Agents_Lab (1)-1.ipynb"
   ```

2. **Execute cells in order:**
   - Click the **Play** button on each cell, or
   - Select a cell and press **Shift + Enter**

3. **Read the questions** and type your answers in markdown cells

4. **Observe the simulation output** to see your robot in action

## 💡 Key Concepts

| Concept | Definition |
|---------|-----------|
| **Agent** | An entity that perceives the environment and acts upon it |
| **Sensor** | Input mechanism that perceives the environment |
| **Actuator** | Output mechanism that acts on the environment |
| **Reflex Agent** | Agent that decides actions based on current inputs only (no memory) |
| **Deterministic** | Environment where outcomes are certain and predictable |
| **Stochastic** | Environment with randomness and uncertainty |
| **Probability** | Measure of likelihood; used to simulate uncertain events |

## 📋 Requirements

- Python 3.6+
- Jupyter Notebook or JupyterLab
- `random` module (included in Python standard library)

## 🔧 Code Highlights

### Simple Reflex Agent
```python
def robot_brain(room_status):
    """Takes in what the robot sees, outputs an action."""
    if room_status == 1:
        return 'CLEAN'
    elif room_status == 0:
        return 'MOVE_RIGHT'
```

### Noisy Sensor Simulation
```python
def sense_environment(actual_room_status):
    """80% accurate sensor, 20% returns UNKNOWN"""
    if random.random() < 0.8:
        return actual_room_status
    else:
        return 'UNKNOWN'
```

## 🤔 Discussion Questions

The notebook includes reflection questions to deepen understanding:

1. Why use numbers (`1`/`0`) instead of strings for room status?
2. What happens if we reverse the robot's rules?
3. Why is the loop boundary condition important?
4. How should the robot handle uncertain sensor readings?

## 🎓 Extensions & Further Learning

After completing this lab, consider:
- **Goal-based agents** that plan ahead to reach a destination
- **Utility-based agents** that optimize multiple objectives (cleanliness vs. battery)
- **Learning agents** that improve their performance over time
- **Multi-agent systems** with multiple robots working together
- **Real sensor integration** with actual IoT devices

## 📚 Related Topics

- Artificial Intelligence (AI)
- Robotics
- Control Systems
- Probability & Statistics
- Algorithm Design

## ✅ Success Criteria

You've successfully completed the lab when:
- [ ] Hallway is cleaned in the basic simulation
- [ ] Resource-constrained simulation runs without errors
- [ ] Sensor diagnostic shows ~20% error rate
- [ ] You understand the trade-offs in agent design

## 📝 License

See LICENSE file for details.

## 🤝 Contributing

This is an educational lab for CMU's AI for Engineers course. Suggestions and improvements welcome!

---

**Last Updated:** August 2026  
**Course:** AI for Engineers  
**Institution:** Carnegie Mellon University