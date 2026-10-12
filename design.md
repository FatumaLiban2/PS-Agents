## Question 1: Designing the Self-Driving Trailer Agent

### 1.1 Introduction

A self-driving trailer can be described as an intelligent agent that operates within Kenya's highway network. Its main objective is to travel from Nairobi, which is the initial state, to Kisumu, which is the goal state. To achieve this objective, the agent must identify possible routes, collect information about its surroundings, select suitable actions and respond to changes in road conditions.

The PEAS framework is used to describe this agent's task environment in terms of its Performance measure, Environment, Actuators and Sensors. We came up with these four components to help explain what the agent is expected to achieve, where it operates, how it interacts with the environment and how it obtains the information needed to make decisions.

### 1.2 PEAS Framework

#### Performance Measure (P)

The performance measure describes the criteria used to determine whether the self-driving trailer is performing its task successfully. The trailer should reach Kisumu safely while following traffic regulations and using an appropriate route.

One important performance measure is safety. The agent should avoid collisions, maintain a safe distance from other vehicles and respond appropriately to pedestrians, obstacles and road signs. Safety is particularly important because the trailer operates in an environment where its decisions can affect other road users.

Another performance measure is successful goal achievement. The agent should reach Kisumu from Nairobi by following a valid route through the highway network. It should also consider the distance travelled and the time required to complete the journey.

Fuel efficiency is another consideration because unnecessary acceleration, braking and detours can increase fuel consumption. The agent should therefore aim to use fuel efficiently while maintaining safe driving behaviour.

Finally, the agent should comply with traffic regulations, including speed limits, traffic signals and road signs. These performance measures help the agent select actions that support a safe and efficient journey rather than focusing only on reaching the destination quickly.

#### Environment (E)

The environment consists of everything outside the agent that it encounters or interacts with while travelling. In this scenario, the environment is Kenya's highway network, with Nairobi as the starting point and Kisumu as the destination.

The environment includes towns and cities along possible routes, such as Nakuru and other connecting towns, as well as roads, junctions, roundabouts and highway intersections. These locations and connections are important when the agent plans its journey.

The environment also includes other vehicles, pedestrians, cyclists, traffic signs, roadblocks and obstacles. Weather conditions, road surfaces, congestion and accidents may affect the trailer's movement and the route it can follow.

The environment is not completely predictable. For example, a road that is clear when the journey begins may become congested later. The agent must therefore consider both the highway network used for route planning and the changing conditions encountered during the actual journey.

#### Actuators (A)

Actuators are the mechanisms through which the self-driving trailer carries out actions and affects its environment. They allow the agent to translate its decisions into physical movements and control operations.

The steering mechanism allows the trailer to change direction when approaching a junction or following a road that curves. The accelerator controls the amount of power supplied to the vehicle, allowing it to increase or maintain its speed. The braking system enables the trailer to slow down or stop when approaching traffic lights, obstacles or other vehicles.

Gear controls help select an appropriate gear for the driving conditions, while indicators communicate intended turns or lane changes to other road users. Headlights, brake lights and other vehicle lights also support safe operation.

For example, when the agent detects a junction on its planned route, it can activate the appropriate indicator and use the steering mechanism to follow the selected road. If an obstacle appears ahead, it can reduce speed or apply the brakes.

These actuators are important because selecting a suitable action during route planning is not enough. The agent must also be able to carry out that action safely.

#### Sensors (S)

Sensors allow the self-driving trailer to collect information about its current state and surrounding environment. The information collected helps the agent understand road conditions, identify possible hazards and decide which actions to take.

Cameras can identify road signs, lane markings, traffic lights and visible obstacles. A Global Positioning System (GPS) receiver helps determine the trailer's current location and supports navigation between towns. Radar can detect nearby vehicles and estimate their distance and relative speed, while LiDAR uses laser measurements to estimate the distance to surrounding objects.

Speed sensors provide information about the trailer's current speed. Additional sensors may monitor conditions such as temperature, rainfall or other environmental factors that could affect driving.

For example, GPS can help the agent determine whether it is approaching a town on its planned route, while a camera can identify a stop sign. Radar can help detect a vehicle ahead, allowing the agent to adjust its speed or maintain a safe following distance.

The information from these sensors enables the trailer to make informed decisions. However, sensors have limitations, and they may not detect every hazard or provide complete information about the environment.

### 1.3 Characteristics of the Agent Environment

The self-driving trailer operates in a real-world environment that can be described using five common pairs of AI environment classifications.

#### Fully Observable or Partially Observable

A fully observable environment is one in which the agent can obtain all the information relevant to its current decision. A partially observable environment is one in which the agent has incomplete information about the current state.

The self-driving trailer operates in a partially observable environment. Although it uses cameras, GPS, radar and other sensors, it cannot detect everything happening around it. For example, another vehicle may be hidden behind a larger truck, or an obstacle may be difficult to see because of poor visibility.

The agent must therefore make decisions using the information available to it while accounting for uncertainty. It may also need to update its understanding of the environment as new sensor information becomes available.

#### Deterministic or Stochastic

A deterministic environment is one in which the outcome of an action is fully determined by the current state and the action taken. In a stochastic environment, outcomes involve uncertainty.

The trailer's real-world driving environment is stochastic because the outcome of its actions may be affected by factors it cannot fully predict or control. For example, another driver may suddenly change lanes, a pedestrian may cross the road unexpectedly, or heavy rain may reduce visibility.

Even when the agent follows its planned route and obeys traffic regulations, these events can affect the journey. The agent must therefore be able to respond to unexpected situations instead of assuming that every action will produce a predictable outcome.

#### Episodic or Sequential

In an episodic environment, each decision can be made independently because one episode does not significantly affect another. In a sequential environment, the current decision can influence later states, decisions and outcomes.

The self-driving trailer operates in a sequential environment because its actions affect what happens next during the journey. For example, selecting a road from Nairobi determines which towns and junctions the trailer may encounter later.

Similarly, braking too late may affect the trailer's position and safety, while choosing a particular route may influence the total distance travelled and the time required to reach Kisumu.

The agent must therefore consider the consequences of its decisions over the entire journey. This is also relevant to the search problem described in the lecture, where a path consists of a sequence of connected states and actions.

#### Static or Dynamic

A static environment does not change while the agent is making a decision, whereas a dynamic environment can change during that process.

The trailer's driving environment is dynamic because road and traffic conditions can change while it is operating. For example, traffic may become congested, a vehicle may stop unexpectedly, or an accident may block a road that was previously available.

These changes may require the agent to reduce speed, stop or consider an alternative route. The agent must continuously monitor its surroundings and update its decisions when necessary.

Although a simplified highway graph used for route planning may remain unchanged during a particular search, the real-world driving environment is dynamic.

#### Discrete or Continuous

A discrete environment consists of distinct states and actions, while a continuous environment involves quantities that can take values across a continuous range.

The physical driving environment of the trailer is mainly continuous because its position, speed, steering angle and travel time can vary over a range of values. For example, the trailer may travel at different speeds depending on traffic and road conditions.

However, route planning can be represented as a discrete search problem. In the highway network, towns such as Nairobi, Nakuru and Kisumu can be represented as individual states, while the roads connecting them represent possible transitions between states.

This distinction is important because the agent may use a discrete graph to compare routes while relying on continuous control of its speed and movement during the actual journey.

### 1.4 Conclusion

The PEAS framework provides a way to describe the task of the self-driving trailer by identifying its performance measures, environment, actuators and sensors. The performance measures guide the agent towards safe and efficient driving, while its sensors and actuators allow it to observe and interact with the environment.

The trailer's real-world environment is partially observable, stochastic, sequential, dynamic and mainly continuous. These characteristics show why the agent must do more than follow a fixed route. It must plan its journey from Nairobi to Kisumu, monitor changing conditions and adjust its actions to reach the destination safely and efficiently.

