Tracking the progress of UW RoboSoccer

We are competing in the 2026 RoboCup in South Korea.
- Building 4 ~50cm tall humanoid robots to play soccer
- Attempting to do so with abstraction, and cheap and accessible hardware
- Most other robots competing are ~$10k each
- Example of robots playing: https://www.youtube.com/watch?v=Vxxrlv6Ohew
- We are trying to revolutionize the competition by introducing full Reinforcement Learning control, from bipedal movements to game theory
- We are also looking for funding! Please reach out!
# Progress
## December 2024
This month the goal is to prepare to develop a working prototype in the new year
- prep BOM
- Redesign
	- focusing on DFM, and light weight
	- CoM, biomechanics research
### Dec 12th:
#### Prototype BOM:

| Part               | Specifications                                                                   | Why Include                                                                                                            | Suggested Links                                                                                                                                                               |
| ------------------ | -------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Actuator/Servo     | - Serial Bus Control<br>- 12V compatible<br>- 30KG torque<br>- Price range $0-50 | - Provides precise movement control<br>- Serial bus allows for complex motion sequences<br>- High torque for stability | [HiWonder HTD-45H](https://www.hiwonder.com/products/htd-45h)<br>[ST3215 Servo](https://www.alibaba.com/product-detail/ST3215-Servo-30KG-Serial-Bus-Servo_1600869438006.html) |
| Controller         | RPi or alternative                                                               | - Central processing unit<br>- Can handle multiple I/O<br>- Good community support                                     | Consider: Raspberry Pi or similar SBC                                                                                                                                         |
| Servo Driver Board | Waveshare Bus Servo Adapter                                                      | - Necessary interface between controller and servo<br>- Handles voltage/signal conversion                              | [Waveshare Bus Servo Adapter](https://www.waveshare.com/bus-servo-adapter-a.htm)                                                                                              |
| Battery            | - 12V<br>- 1200mAh                                                               | - Powers entire system<br>- Rechargeable<br>- Sufficient capacity for extended use                                     | [KBT 1200mAh](https://www.amazon.com/KBT-1200mAh-Rechargeable-Replacement-Compatible/dp/B0C23Y3VZK)                                                                           |
| Camera + IMU       | Waveshare RP2040 LCD 1.28"                                                       | - Combined vision and motion sensing<br>- Integrated display for feedback<br>- Compact form factor                     | [Waveshare RP2040 LCD](https://www.waveshare.com/rp2040-lcd-1.28.htm)                                                                                                         |
| Voltage Converter  | 12V to 5V 3A                                                                     | - Necessary for powering 5V components<br>- High current capacity for reliability                                      | TBD                                                                                                                                                                           |
| Audio System       | - Microphone<br>- Speaker<br>- Amplifier                                         | - Enables audio interaction<br>- Feedback system<br>- User communication                                               | TBD                                                                                                                                                                           |
| Connectors         | Molex style                                                                      | - Reliable connections<br>- Easy maintenance<br>- Industry standard                                                    | TBD                                                                                                                                                                           |
#### Hardware Architecture
made with Lucid
![[Pasted image 20241211175157.png]]
## November 2024
- Initial Mechanical design completed:
![[Pasted image 20241129143915.png|500]]

- Currently research URDF and XML to be used in Mujoco Simulation

We are also rebuilding [dm_control](https://github.com/google-deepmind/dm_control) with more specialized control environment for our RL training scenarios: https://github.com/UW-RoboSoccer/soccer_env