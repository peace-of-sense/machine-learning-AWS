# Reinforcement Learning

In *reinforcement learning* (RL), an *agent* is trained to achieve a goal based on the feedback it receives as it interacts with an *environment*. It collects a number as a *reward* for each *action* it takes. Actions that help the agent achieve its goal are incentivized with higher numbers. Unhelpful actions result in a low reward or no reward.

With a learning objective of **maximizing total cumulative reward**, over time, the agent learns, through trial and error, to map gainful actions to situations. The better trained the agent, the more efficiently it chooses actions that accomplish its goal.

- **Agent:** The piece of software you are training is called an agent. It makes decisions in an environment to reach a goal.
- **Environment:** The environment is the surrounding area with which the agent interacts.
- **Reward:** Feedback is given to an agent for each action it takes in a given state. This feedback is a numerical reward.
- **Action:** For every state, an agent needs to take an action toward achieving its goal.

### Application

- Playing Games
- Video game level design
- Wind energy optimization
- Industrial robotics
- Fraud detection
- Stock trading
- Autonomous driving

### Basic RL terms

<img src="https://video.udacity-data.com/topher/2021/April/6081a9f8_l3-ml-with-aws-rl-terms/l3-ml-with-aws-rl-terms.png" alt="Image contains icons representing the basic RL terms: Agent, Environment, State, Action, Reward, and Episode." style="zoom:67%;" />

**Agent**

- The piece of software you are training is called an agent.
- It makes decisions in an environment to reach a goal.
- In AWS DeepRacer, the agent is the AWS DeepRacer car and its goal is to finish laps around the track as fast as it can while, in some cases, avoiding obstacles.

**Environment**

- The environment is the surrounding area within which our agent interacts.
- For AWS DeepRacer, this is a track in our simulator or in real life.

**State**

- The state is defined by the current position within the environment that is visible, or known, to an agent.
- In AWS DeepRacer's case, each state is an image captured by its camera.
- The car’s initial state is the starting line of the track and its terminal state is when the car finishes a lap, bumps into an obstacle, or drives off the track.

**Action**

- For every state, an agent needs to take an action toward achieving its goal.
- An AWS DeepRacer car approaching a turn can choose to accelerate or brake and turn left, right, or go straight.

**Reward**

- Feedback is given to an agent for each action it takes in a given state.
- This feedback is a numerical reward.
- A reward function is an incentive plan that assigns scores as rewards to different zones on the track.

**Episode**

- An episode represents a period of trial and error when an agent makes decisions and gets feedback from its environment.
- For AWS DeepRacer, an episode begins at the initial state, when the car leaves the starting position, and ends at the terminal state, when it finishes a lap, bumps into an obstacle, or drives off the track.

In a reinforcement learning model, an **agent** learns in an interactive real-time **environment** by trial and error using feedback from its own **actions**. Feedback is given in the form of **rewards**.

<img src="https://video.udacity-data.com/topher/2021/April/6082ffe0_l3-ml-with-aws-all-together-now/l3-ml-with-aws-all-together-now.png" alt="In a reinforcement learning model, an agent learns in an interactive real-time environment by trial and error using feedback from its own actions. Feedback is given in the form of rewards." style="zoom:67%;" />



## Reinforced Learning into Action in AWS DeepRacer

[AWS DeepRacer](https://aws.amazon.com/deepracer/?utm_source=Udacity&utm_medium=Webpage&utm_campaign=Udacity AWS ML Foundations Course) is a combination of a [physical car](https://aws.amazon.com/deepracer/robotics-projects/?utm_source=Udacity&utm_medium=Webpage&utm_campaign=Udacity AWS ML Foundations Course) and a [virtual simulator](https://console.aws.amazon.com/deepracer/home?region=us-east-1&utm_source=Udacity&utm_medium=Webpage&utm_campaign=Udacity AWS ML Foundations Course#createModel) in the [AWS Console](https://aws.amazon.com/console/?utm_source=Udacity&utm_medium=Webpage&utm_campaign=Udacity AWS ML Foundations Course), the [AWS DeepRacer League](https://aws.amazon.com/deepracer/league/?utm_source=Udacity&utm_medium=Webpage&utm_campaign=Udacity AWS ML Foundations Course), and [community races](https://console.aws.amazon.com/deepracer/home?region=us-east-1&utm_source=Udacity&utm_medium=Webpage&utm_campaign=Udacity AWS ML Foundations Course#communityRaces).

An AWS DeepRacer device is not required to start learning: you can start now in the AWS console. The 3D simulator in the AWS console is where training and evaluation take place.

### New Terms

In AWS DR, the reward functions are split up inform of grids. Each grid has its own point. We an train the agent by Exploration or Exploitation methods.

<img src="https://video.udacity-data.com/topher/2021/April/608893cc_screen-shot-2021-04-27-at-3.44.12-pm/screen-shot-2021-04-27-at-3.44.12-pm.png" alt="Each square is a state. The green square is the starting position, or initial state, and the finish line is the goal, or terminal state." style="zoom: 50%;" />

Each state on the grid is assigned with a reward function. We can encourage our agent to quickly finish the lap by assigning maximum rewards at specific direction/state. The reward function is actual conde that you write to help your agent to determine that a move made is good or bad.

<img src="https://video.udacity-data.com/topher/2021/April/60889441_screen-shot-2021-04-27-at-3.46.11-pm/screen-shot-2021-04-27-at-3.46.11-pm.png" alt="The squares containing exes are the track edges and defined as terminal states, which tell your car it has gone off track. " style="zoom:50%;" />

| Exploration                                                  | Exploitation                                                 |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| In exploration the DeepRacer is let to explore the environment in random direction. More training the agent  gets more it learns about the environment. | In exploitation, the DeepRacer exploits or uses information from previous experiences to help reach its goal. Different training algorithm utilizes exploration and exploitation differently. |

**Reward graph:** While training your car in the AWS DeepRacer console, your training metrics are displayed on a reward graph. Plotting the total reward from each episode allows you to see how the model performs over time. The more reward your car gets, the better your model performs.

