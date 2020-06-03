# Boids Simulation 

## Description 

Initially, we started building a Maplestory clone in Unity but, due to coronavirus constraining our workflow, we decided to do a project that each project member could build individually and since everyone had a basic grasp on Unity at that point, we built this Boids simulation! Inspiration and guidance from Sebastian Lague and Board to Bits on YouTube. 

# Overview 

Boids is a classic project explored in many computer science courses around the world; the project is used as an introduction to programming dynamic behaviors, graphical applications and just how cool coding can be! It can be built in many different languages quickly - such as JavaScript, C++. We used Unity (a video game engine) and C#, as Unity has built-in physics capabilities and C# is its scripting language. 

Birds in real life tend to flock together but also exhibit avoidance from their neighbors and tending towards the general direction of the clock; evolutionarily, birds that stray from the pack probably don’t make it too long and those that hit others can't fly very effectively. In general, this is represented in lots of migrational patterns, from fish to butterflies to birds and even bacteria! More specifically, living organisms seemingly gravitate towards the center of mass of a particular flock; as they move, they go with the flow of where the center is and follow the pack, separating themselves as needed. The project is also just really relaxing to look at if you're running it in the background; feel free to use a gif of it as your screensaver! 

## Behavior 

Boids exhibit three behaviors: avoidance, direction and cohesion; we describe them briefly here. 

## Avoidance

Avoidance basically means… avoiding things. Each of the birds want to stay away from the others and avoid collisions. We used Unity’s physics engine to send out a ray of a certain radius on each of the birds. Whenever it encountered another bird, it kept track of the count and the other bird’s position. Then, it took the difference between the current bird and the neighboring bird’s positions and added it to a vector. Finally, it normalized the resulting vector and told the bird to move in that direction. The birds will move even more exaggerated if we weighted this vector more. 

## Direction 

Direction was pretty easy to implement. Again, we used the Unity physics engine to find the neighboring birds. Then, we found the direction vector of all the birds and normalized it. The birds by default simply move in whatever direction they face. If you weighted this behavior less in the composite behavior of the flock, then the birds would actually diverge more - and if you weighted it higher, they’d try a lot more to stay in the same direction as their neighboring ones. 

## Cohesion

Basically, cohesion means that a bird wants to stay close together to its neighbors. Obviously, if a bird strayed away too far from the flock, then it’ll die in real life. What we did was used each of the neighboring bird’s positions and normalized it into a single vector, somewhere in the middle of the neighbors. Then, we tell the bird to try its best to fly towards that direction. Because the flock’s total position is always changing, this will steer the bird into some direction, and because there’s tons of birds in a particular area, they’ll all move somewhat randomly but in a general direction. For this script, we inverted the resulting movement vector, so the higher the number, the more randomly the birds will fly. 

## Putting it together

So, to actually simulate real-world behaviors, we used somewhat of a neural-network approach to the flock’s overall behavior. We created a composite behavior that calculated each of the individual behaviors vectors for a bird, and then multiplied them by some weight and then added them together. This allowed us to test out how different behaviors, when weighed higher/lower, would affect the flock’s overall behavior.

# Conclusion

## Remarks 

We learned a lot of different things while working on this project; we got to brush up on our linear algebra, see how a big project fits together and also create emergent behaviors from things that seemingly aren't compatible. We did some other stuff with linear interpolation to change the color of a bird if they're straying too far away from the flock, and also implemented a way to keep the birds at the center of the screen so they don't eventually fly off into the distance - which is kind of metaphorical! 

## Things to add 

If you're looking at this project in the future, feel free to download it and work on it yourself; some interesting features you can add: object detection and avoidance, death upon veering away from a cluster, predators/prey/food (some survival system), and much more. 

The labs/slides we provided to our team is linked <a href="https://drive.google.com/drive/folders/1SalFw94R6eWkNtrvqDdWp6yItYKvSBMi?usp=sharing"> here </a>

## Installation

Install Unity, if you haven't done so already; download the project and then simply import it and run. 
