# Desafio Robótica 2021
Author: Brenda Silva de Alencar

## Mission
  The robot must navigate autonomously, avoiding obstacles, until it reaches the region illuminated with a stop sign in up 2 minutes. This task should be developed in the Webot software environment, utilizing the Pioneer 3-DX Robot . 

## The Solution
  To complete this task, the robot was equipped with three light sensors installed on the top of the shape separed between 40 degrees,that measures the irradiance of light in three directions. Furthermore, the robot is assembled with motors featuring 500-tick encoders in the 2 wheels and 16 ultrasonic sensors which enables the robot navigate in the environment and not collide with the objects.
  
figure

  The controller used has two importants point, avoid collision and detect the arrival point. To the first one, the 16 distance sensors read the environment and measure the distance between the robot and the environment, so when this measurement is less than the minimum distance defined, the robot  must  rotate in the opposite direction. This happen by modifying the speed of the two wheels, first the distance is readed by one sensor and the "speed_modifier" is calculated, then is multiplies this variable by a factor called "wheel_weight", which takes into account the orientation of each sensor on the robot. Therefore, the Pioneer controller sum all these weights and applies in to the two wheels, if the sum of one side indicates that it is too close to an obstacle, the robot will rotate to the opposite side, but if not, it will continue in a straight line. To the second point, the three light sensors read the environment, if the left one measures the irradiance more than 65 W/m2 (threshould that indicate a higher light presence), the robot will turn in this direction. The same happens with the sensor on the right, this mechanism must move the robot in favor of the light. Lastly, when the three light sensors detect the light presence for a significant time (4 seconds), it indicate that the robot has completed the mission.
  
## Conclusion and results
  The control used shows a good performance, the robot can find the arrival point in up to two minutes without many difficulties, even if it has taken a longer route
  
  figure


