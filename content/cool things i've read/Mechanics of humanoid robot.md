https://www.tandfonline.com/doi/epdf/10.1080/01691864.2020.1813624?needAccess=true
legs of humanoid robot are designed to
1. recudece model error
2. reduce leg inertia

for 1.: each link must have high stiffness against bending nad torsion, and 2.: end link is designed to have a low mass

brought up an interesting point:
high CoM in bipedal robots is benefitial
1. simplifies dynamics: when robot is standing on one leg, the bipedal robot's dunamics can be modeled as a inverted pendulum. nad mass of robot can be considered as concentrated at the CoM
2. reduced lateral motion: 
![[Pasted image 20241215125650.png]]
![[Pasted image 20241215125653.png]]
According to these equations, when CoM (z) is higher, robot requires less lateral swing of the CoM for given a single support period. 
3. angular momentum reduction: high CoM position helps reduce angular momentum about the fore-aft axis, esp when wallking fast. because excessive anglar momentum make robot less stable and less efficient
4. higher CoM can contribute to recuced angular momentum, allows for more efficient movement patterns

walking cycle control:
1. single support phase: ![[Pasted image 20241215130036.png]]
	- y is posiition, Ts is time on one foot, z is CoM height, g is grav
2. Weight transfer
	- before lifting foot, the robot shifts its COM towards supporting foot
	- must be a precise shift
	- controlled by monitoring **ZMP** -- point where robot's weight and intertial forces are balanced
3. Real-time sensors measure the robot's actual position and forces
	- compres theres measurements to ideal math model
	- adjusts using hips and nakle actuators to maintain correct sway
	- if sway gets too large, robot can take wider steps
4. foot placement
	- robot plans where to place each foot based on desired sway pattern
	- wider steps create more stability but more energy and larger sway
	- narrower steps = more energy efficeinet but need more control precision
