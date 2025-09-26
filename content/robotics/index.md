+++
title = "Robotics"
template = "article.html"
[extra]
banner = "banner.webp"
+++

{{ youtube(id="P6ZmZoa7wng") }}

<!-- {{% center %}} -->
### [Programming Notebook](https://drive.google.com/file/d/1hd0VK4iIhffCv_00uxb7vwG03PvXW3pT/view?usp=sharing)
Recommended Pages: 39 - 62, 67 - 82
<!-- {{% center %}} -->
# Team 8568C Cowboys

I was the lead programmer for the VEX Robotics team 8568C from North Andover, Massachusetts. As a team, we placed Math Division Finalist at the 2025 VEX World Championship, tournament finalist at the 2025 Massachusetts State Championship, and won the THINK award (Awarded for Programming Strategy) at the 2024 Southern New England Regional Championship.

## Knights Library
The Knights Autonomous Library includes all of the code necessary to power a VEX Robotics team. Essential features include:
- Drive control feature: bindings for input maps (inspired by game development projects) which allows for creation of button functions. Joystick input includes input curve to allow for faster, more consistent driving
- Odometry system with easily configurable tracking wheels and inertial sensors for almost all configurations. Used to localize the robot’s position on the field, which is displayed on a custom VEX brain display
- Motion algorithms for robot movement: heavily optimized pure pursuit algorithm (for curved and path following movement) and functional approach to PID (forward/backward and turning).
- Visual path planner: can create full routes with lateral, turn, and curved movements without code

### Constraints
Key constraints of VEX robotics system include:
- Only VEX sensors can be used: third-party inertial sensors for odometry and microcontrollers are prohibited. VEX sensors also can be error-prone, so I needed to write code to account for this.
- Time limits: limited autonomous periods require us to optimize our movement speed
- Propagated Error: VEX rules are extremely strict. If a propagated error results in us breaking a rule (like autonomously picking up a third ring when only two are allowed), our autonomous run is disqualified. Therefore, we have switched to using global movements to ensure that our robot always goes to the correct position.

### Visual Path Planner Creation Process
**Version 1** was made with Pygame. Inputs in text form allowed for simple lateral (forward/backward) and turn movements and were displayed on a map. This approach was great for a MVP, but it ended up not being performant enough to handle larger paths with the frame-based rendering of Pygame.
 
**Version 2** had a similar backend, but incorporated pure pursuit and could create curved paths. Last year’s competition had many obstacles so I built a graph structure with each box corresponding to a specific game field tile. I used graph search algorithms followed by bezier curves to create the arc between any two tiles. 

**Version 3** I used Rust, HTML, CSS, and Javascript to upgrade the backend and visuals in the current version. It also incorporates lateral movements, turns, path generation with bezier curves, and has an input system to command robot components (intake, wings, etc). My teammates can use it to easily create autonomous routes.

### Reflection
Some of my earlier work had mistakes, like using time-based lateral movement instead of global position. These caused inaccuracy, resulting in low scores in programming skills and autonomous win points. However, these earlier stages were necessary for me to see why I needed to optimize motion algorithms or why I needed to incorporate features such as global movement or PID in our current design.

If I had to do things differently, I would have been more flexible in shifting methods. I often would spend a lot of time trying to make one certain method for something work when it wasn't the best choice. This would make the autonomous routines really hard to make, as I was building them off a flawed system. These autonomous routines would also commonly fail, which would lose us matches and hurt our placement on score leaderboards. As I've gotten better at robotics and engineering in general, I've worked to address this issue, often testing and prototyping multiple different solutions for different problems. While this adds more work upfront, it ends up making the use of the solutions a lot easier.
