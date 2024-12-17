**Quick video of the robot operating: [dummy_move.MP4](https://drive.google.com/file/d/19syZx1zGBMIvCTpJkcvSTVYOZutUH3FT/view?usp=sharing)**
# Context

Inspired by Tony Stark's Dum-E and U, this project explores practical robotic assistance in desktop environments. The goal was to create a robust, precise robotic arm capable of real-world manipulation tasks while being adaptable to various control schemes.

![[Pasted image 20241109150655.png|300]]

I named it "**U**" as a nod to Tony Stark's chaotic robot U. 
A few requirements I had before making this project:
- It must be **compact**: Fit on my desk without taking up too much space
- It must be **smooth**: Needed precise, fluid movements for reliable operation
- It must be **powerful**: Required enough strength to be useful, not just a toy
- It must **look** **sick**: If you're building a robot assistant, it better looks fire!
# Firmware/Control Software
- [[Dummy Control System]]
- [[Stepper Motor Control System]]
- [[6-DOF Robot Kinematics]]
- [[Motion Control System]]
- [[Motor Driver and FOC]]
- [[Encoder Calibration System]]
# Mechanical Design
## Body/Joints
I arrived at this final design after 3 prototyping iterations and 144 versions.
FEA of each joint and connection was conducted to validate the structural integrity of the robot.
In the end, the CNC version of the robot can hold up to 2kg of mass on its end effector, which is equivalent to exactly 7 of my favourite Chinese drinks:
I am currently finding materials and redesigning the robot for 3D printing, to make the process cheaper and more streamlined.

![[Pasted image 20241124201829.png|200]]
## Actuator Design
The original goal was to 3D print custom harmonic actuators, but the tolerance is just too tight for the operation to be smooth and accurate. But here is my design anyway.
![[Pasted image 20241207135431.png]]
A harmonic reducer (or harmonic drive) works on the principle of mechanical wave propagation using three main components:
- A wave generator (input)
- A flex spline (flexible gear)
- A circular spline (rigid outer gear)
The key to its operation is the small difference in the number of teeth between the flex spline and circular spline. The flex spline 2 fewer teeth than the circular spline. When the wave generator rotates, it creates an elliptical shape in the flex spline, causing its teeth to mesh with the circular spline at two points. This tooth difference creates a slow, precise rotation of the output.
The formula used to calculate the ratio of input vs. output is ZcZc-Zf, where Z_c and Z_f are the circular and flex spline respectively. In this case, the ratio is 50. 
Then I made and prototyped a smaller version which would fit better for my application with a torque ratio of 1:20:
 ![[Pasted image 20241109151433.png]]

After playing around with custom 3D-printed actuators, I folded and opted for an off-the-shelf harmonic reducer because of issues with accuracy and friction with PLA.
# Next Steps
I designed Dummy with 7 degrees of freedom to mimic a human arm, making it adaptable for various robotic applications:
- Adding a claw end effector transforms it into a functional pick-and-place robotic arm
- Mounting it on a humanoid frame (which I named Trumbo) creates a basic humanoid robot
- Integrating it with a mobile base similar to a Roomba enables movement capabilities
While currently a conceptual design, Dummy's modular nature opens up endless possibilities for future applications.


![[Pasted image 20241109151526.png]]