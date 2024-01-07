# fall2023-robkine
Multipart project in the course MEGN544 Robot Mechanics: Kinematics, Dynamics, and Control in Fall 2023 at the Colorado School of Mines.

The project is completed using MATLAB with Simulink.

Part 1: transform from 2D points for the a trajectory resembling the letters CSM (standing for Colorado School of Mines) to 3D points and plot those 3D points with local coordinates, where the x-axis points at the next point in the trajectory.

Part 2: start using MATLAB Simulink to trace the CSM 3D points, stopping at each point, with a sample controller already given by the instructor, using theta and theta dot error feedback with PID gains.

Part 3: the controller only implements theta-only (configuration space) open loop control. There is no feedback
mechanism on the end effector location. We only feed the joint angles and joint rates as desired into the theta
controller.

Part 4: we have the feedback transform (actual) to find the transform error, which would eventually be multiplied with the gain to have an amount of error in the twist (operational space rates) vector to correct the arm trajectory. In doing so, we have a way to address the errors that we fail to anticipate beforehand that would put the end effector at a location other than desired. We also use the velocity Jacobian (Jv) inverse to go from operationalspace velocities to joint space rates (theta dots). The joint space rates were the control signal to feed into the theta controller in Part 4. Laser feedback is also put into use in Part 4.

Part 5: on top of the feedback mechanisms of seen in Part 4, it includes not only operational space velocities but also pose (position and angular). Jv is now used to calculate the actual operational space acceleration vector. The control acceleration vector is used with Jv inverse to generate joint accelerations. With joint accelerations, Newton Euler algorithm is user for inverse dynamics to calculate torque control signals.
