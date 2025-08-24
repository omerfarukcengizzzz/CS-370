# Pirate Intelligent Agent - Deep Q-Learning Project

## CS 370: Current/Emerging Trends in Computer Science

### Project Overview
This repository contains my implementation of an intelligent agent that uses deep Q-learning to navigate a treasure maze. The pirate agent learns to find optimal paths to treasure through reinforcement learning, demonstrating practical applications of neural networks and Q-learning algorithms in solving pathfinding problems.

---

## Project Summary

### What Code Was I Given?
The project provided me with essential starter code that formed the foundation of the treasure hunt game:

- **TreasureMaze.py**: A complete environment class that manages the 8x8 maze, handles agent movement, tracks game states, and calculates rewards. This class provided the game mechanics including the reward system (-0.04 for moves, -0.75 for invalid actions, +1.0 for finding treasure).

- **GameExperience.py**: An experience replay system that stores episodes (state, action, reward, next_state, game_over) and enables the agent to learn from past experiences. This class implements the memory buffer and provides methods for storing and sampling experiences.

- **Jupyter Notebook Skeleton**: A partially completed notebook with helper functions including `build_model()` for creating the neural network, `play_game()` for testing the trained agent, and `show()` for maze visualization.

### What Code Did I Create?
I developed the core Q-training algorithm that brings the intelligent agent to life:

- **Q-Training Algorithm Implementation**: Created a complete deep Q-learning training loop that includes:
  - Epsilon-greedy action selection for balancing exploration (10%) and exploitation (90%)
  - Episode management and game state tracking
  - Experience replay integration with batch training
  - Dynamic epsilon adjustment (reducing to 5% when win rate exceeds 90%)
  - Win rate monitoring and completion checking
  - Training optimization achieving 100% success rate at epoch 8,338

The algorithm successfully trains a neural network to navigate from any starting position to the treasure, learning optimal paths through trial and error combined with reward-based feedback.

---

## Reflections on Computer Science

### What Do Computer Scientists Do and Why Does It Matter?

Computer scientists solve complex problems by creating algorithms and systems that can process information, make decisions, and learn from data. In this project, I acted as a computer scientist by implementing a reinforcement learning solution that teaches an agent to solve a pathfinding problem autonomously. 

This matters because the techniques I used here—deep Q-learning, neural networks, and reinforcement learning—are the same foundations powering real-world applications like autonomous vehicles, robotics, game AI, and recommendation systems. By teaching a pirate to find treasure, I'm actually working with the same principles that help robots navigate warehouses, assist doctors in diagnosis, or optimize traffic flow in smart cities.

### How Do I Approach Problems as a Computer Scientist?

My approach to this problem followed a systematic methodology:

1. **Understanding the Problem Space**: First, I analyzed the maze environment, understanding the state representation (64-element vector), action space (4 directions), and reward structure.

2. **Decomposition**: I broke down the complex problem into manageable components—state observation, action selection, experience storage, and network training.

3. **Algorithm Selection**: I chose deep Q-learning because it's well-suited for problems with discrete action spaces and can handle the complexity of learning optimal policies in maze environments.

4. **Iterative Development**: I implemented the solution incrementally, testing each component and monitoring metrics like loss and win rate to ensure the agent was learning effectively.

5. **Optimization**: I tuned hyperparameters such as exploration rate, training epochs, and batch size to achieve optimal performance.

This systematic approach—understanding, decomposing, implementing, testing, and optimizing—is how computer scientists tackle problems across all domains.

### What Are My Ethical Responsibilities?

As a computer scientist, I have significant ethical responsibilities to both end users and organizations:

**To End Users:**
- **Transparency**: I must ensure that AI systems I develop are understandable and their decision-making processes can be explained. In this project, I can clearly articulate how the agent makes decisions based on Q-values.
- **Reliability**: Systems must work as intended. My agent achieving 100% success rate demonstrates commitment to creating reliable solutions.
- **Safety**: While this is a simple game, the same algorithms could control real-world systems. I must consider potential failures and edge cases.

**To Organizations:**
- **Efficiency**: I have a responsibility to create efficient solutions. My implementation balances training time (31 minutes) with performance (100% success rate).
- **Maintainability**: Code should be well-documented and structured for future developers. My implementation includes clear comments and follows best practices.
- **Honest Representation**: I must accurately represent capabilities and limitations. While my agent performs perfectly in this controlled environment, I understand it wouldn't immediately transfer to different maze configurations without retraining.

**Broader Implications:**
The reinforcement learning techniques I've implemented here could be applied to critical systems like healthcare, criminal justice, or financial services. I recognize that biases in training data, reward structures, or algorithm design could have serious real-world consequences. As I continue developing AI systems, I must always consider:
- Who might be affected by the system's decisions?
- What biases might be present in the training process?
- How can I ensure fairness and equity in AI applications?
- What safeguards are needed to prevent misuse?

---

## Technical Details

### Neural Network Architecture
- Input Layer: 64 neurons (flattened maze state)
- Hidden Layer 1: 64 neurons with PReLU activation
- Hidden Layer 2: 64 neurons with PReLU activation  
- Output Layer: 4 neurons (Q-values for each action)
- Optimizer: Adam
- Loss Function: Mean Squared Error (MSE)

### Training Parameters
- Episodes to 100% Win Rate: 8,338
- Training Time: 31.67 minutes
- Memory Buffer Size: 512 experiences
- Batch Size: 32
- Training Epochs per Game: 8
- Discount Factor (γ): 0.95
- Initial Exploration Rate (ε): 0.1
- Reduced Exploration Rate: 0.05 (after 90% win rate)

### Performance Metrics
- Final Win Rate: 100%
- Final Loss: 0.0213
- Success from All Starting Positions: Yes

---

## Repository Contents
- `TreasureHuntGame.ipynb` - Complete implementation with Q-learning algorithm
- `TreasureMaze.py` - Environment class for maze and game mechanics
- `GameExperience.py` - Experience replay system for agent learning
- `Design_Defense.docx` - Detailed analysis of the implementation approach
- `README.md` - This file

---

## Future Improvements
- Implement prioritized experience replay for faster learning
- Experiment with different neural network architectures
- Add visualization of Q-values during training
- Extend to larger mazes and dynamic obstacles
- Implement transfer learning for different maze configurations

---

## Acknowledgments
This project was completed as part of CS 370 at Southern New Hampshire University. The foundational code structure was provided by the course, and the Q-learning implementation represents my original work in applying reinforcement learning concepts to solve the pathfinding challenge.
