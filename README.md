# SwarmDynamics
Implementation of reservoir computing in swarm dynamics using Boids model introduced by Reynolds. It works on simulating real-life animal flocking behaviour and is more complex in comparison to particle systems.

* Findings from the paper linked: https://dl.acm.org/doi/10.1145/37402.37406
* https://api.research-repository.uwa.edu.au/ws/portalfiles/portal/105998910/Reservoir_Computing_with_Swarms_AAM.pdf : Lymburn, Thomas, Shannon D. Algar, Michael Small, and Thomas Jüngling. "Reservoir Computing with Swarms." Complex Systems Group, Department of Mathematics and Statistics, The University of Western Australia, 10 February 2021.

## History of Animates:
* Artifical animals are called Animates.
* Flocking behaviour of birds was simulated by Reynolds who called the artifical birds as "boids".
* Main idea behind boids model is to avoid collisions and stay within the flock
* Model tackles two main things: Collision avoidance (static + dynamic) and velocity steering mechanism

## Boids model Versus Particle systems:
* Boids behaviour model has objects that have geometrical shapes while Particles systems are associated with fuzzy objects. This makes Boids model more complex since we would now also talk about orientation of the objects in the flock.
* Simulation of particles less complex in comparison to Boids model. Particles in particle systems do not interact with one another while that is not the case for Boids which depends on internal and external states.

# Boids Model:
Talks about balanced yet opposing behaviours of staying within the flock as well as avoiding collision. Amount of thinking a bird has to do to flock must be independent of the number of birds in the flock. We look at 4 different forces mentioned in the paper on "Reservoir Computing with Swarms".

* Without a predator:
    * Works based on 3 major forces: Cohesion, Alignment and Homing forces. Equations can be retrieved from the papers cited above.
    * An additional fricitional force is added as well to achieve a required target speed for each agent/boid in the swarm.
    * The total force is calculated with weights provided for each of the above mentioned forces.
    * This total force is now passed through a sigmoid wrapping. To put it vaguely, it accounts for the ideal vs possible motion of the boids.
* With a predator:
    * An additional force is added for a predator to influence the motion of the swarm. 
    * This allows the swarm to maintain a minimum distance with the predator and ensure the movement of the swarm is repulsive when it falls too close to the predator hence avoiding its (predator's) reach.
    * For the sake of simplicity, only a single predator moving in a lorenz 63 chaotic system has been introduced. 

# Sequence of Code Improvements:


*   Step 1: Produce code in python for a simple agent-based model (ABM) following Reynold's boids model without any predators.
*   Step 2: Introduce a stationary predator and notice how the repulsive force added to the total force for each agent is affects the motion of the swarm around the predator.
*   Step 3: Allow the predator to move in a chaotic system (in our case, a Lorenz63 system) and notice how the boids dynamically change their motion to repel the moving predator. 
