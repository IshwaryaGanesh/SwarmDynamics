# SwarmDynamics
Implementation of reservoir computing in swarm dynamics using Boids model introduced by Reynolds. It works on simulating real-life animal flocking behaviour and is more complex in comparison to particle systems.

# Findings from the paper linked: https://dl.acm.org/doi/10.1145/37402.37406

## History of Animates:
* Artifical animals are called Animates.
* Flocking behaviour of birds was simulated by Reynolds who called the artifical birds as "boids".
* Main idea behind boids model is to avoid collisions and stay within the flock
* Model tackles two main things: Collision avoidance (static + dynamic) and velocity steering mechanism

### Collision Avoidance:
Based on boids' flockmates (immediate neighbours') and their relative positions only and not their velocities at all. Ensures the minimum required separation distance. Static

### Velocity Matching
Maintains the minimum required separation distance at all points in time. Dynamic

### Velocity steering mechanism: (Flock centering)
Each boid tries to be at the centre of its flock (which consists of its immediate neighbours)

## Boids model Versus Particle systems:
* Boids behaviour model has objects that have geometrical shapes while Particles systems are associated with fuzzy objects. This makes Boids model more complex since we would now also talk about orientation of the objects in the flock.
* Simulation of particles less complex in comparison to Boids model. Particles in particle systems do not interact with one another while that is not the case for Boids which depends on internal and external states.

# Boids Model:
Talks about balanced yet opposing behaviours of staying within the flock as well as avoiding collision. Amount of thinking a bird has to do to flock must be independent of the number of birds in the flock.
## Geometric Flight:
* This is governed by three things: the translation (moving from one place to another), pitch (tilting up and down) and yaw (moving left and right)


# To Do:


*   Check how boids can be coded in matlab (with and without predator)
*   How does swarms vs swarms function. (more than one predator moving with a boids model and each member moves in a lorenz63 system)
