Model Predictive Controller Project

The model
The model includes the vehicle's x/y coordinates, orientation angle, velocity, cross-track error, and orientation angle error. The actuators are acceleration and steering angle. These are used in accordance with the update equations to calculate the state for the current timestep. The update equations are the ones provided in the Udacity Lesson 19: Model Predictive Control.

Timestep Length and Elapsed Duration (N & dt)
The values used are N = 10 and dt = 0.1; this was the suggested values. After testing around using other values, it was hard to find better results. These values allow for a one second window to determine a new path. Other values tried for N were 5, 8, 15, 20. Values for dt tried were 0.2, 0.05, 0.12. These did not prove to be as good as N = 10 and dt = 0.1.

Polynomial Fitting and MPC Preprocessing
The waypoints are preprocessed by transforming them to a basic xy coordinate with the vehicle being the origin. 

Model Predictive Control with Latency
Dealing with latency in the simulator was harder than expected. To deal with it, an if statement was created to account for latency to use previous actuations. Also, assigning appropriate costs helped in dealing with the latency.