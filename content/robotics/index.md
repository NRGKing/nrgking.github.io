+++
title = "Robotics"
template = "article.html"
[extra]
banner = "banner.webp"
+++

{{ youtube(id="P6ZmZoa7wng") }}

### [Programming Notebook](https://drive.google.com/file/d/1hd0VK4iIhffCv_00uxb7vwG03PvXW3pT/view?usp=sharing)

## Team 8568C Cowboys / Knights Library

The Knights Autonomous Library includes all of the code necessary for VEX teams to program a robot. Essential features include:
- Drive control feature: bindings for input maps (inspired by game development projects) which allows for creation of button functions. Joystick input includes input curve to allow for faster, more consistent driving
- Odometry system with easily configurable tracking wheels and inertial sensors for almost all configurations. Used to localize the robot’s position on the field, which is displayed on a custom VEX brain display
- Motion algorithms for robot movement: heavily optimized pure pursuit algorithm (for curved and path following movement) and functional approach to PID (forward/backward and turning). Currently working on move to position with heading
- Visual path planner: can create full routes with lateral, turn, and curved movements without code

### Visual Path Planner Creation Process
**Version 1** was made with Pygame. Inputs in text form allowed for simple lateral (forward/backward) and turn movements and were displayed on a map. This approach was great for a MVP, but it ended up not being performant enough to handle larger paths with the frame-based rendering of Pygame.
 
**Version 2** had a similar backend, but incorporated pure pursuit and could create curved paths. Last year’s competition had many obstacles so I built a graph structure with each box corresponding to a specific game field tile. I used graph search algorithms followed by bezier curves to create the arc between any two tiles. Since curves weren’t integrated with lateral and turn movements, I used Rust, HTML, CSS, and Javascript to upgrade the backend and visuals in the current version. It also incorporates lateral movements, turns, path generation with bezier curves, and has an input system to command robot components (intake, wings, etc). My teammates can use it to easily create autonomous routes.

### Reflection
Some of my earlier work had mistakes, like using time-based lateral movement instead of global position. These caused inaccuracy, resulting in low scores in programming skills and autonomous win points. However, these earlier stages were necessary for me to see why I needed to optimize motion algorithms or why I needed to incorporate features such as global movement or PID in our current design.

If I had to do things differently, I would have been more flexible in shifting methods. Earlier versions of the library were rigid. I’ve found that creating different versions to try and compare is useful in optimization. For example, using only PID or only pure pursuit wouldn’t be successful, but a mix of them works well.