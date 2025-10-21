# Trail Follower

Implement a more precised distance control to follow the trapezoidal trail in the lab.
Use the encoders to sense and adjust your robot's pose (position and orientation).

![trail_follower](/images/follow_trail.jpg)

## Requirements

> [!IMPORTANT]
> Demo your robot to Dr. Zhang to redeem the credits.

### 1. Plan Trajectories

#### 1.1. Encoder Guided Linear Motion

Assume your robot will drive **straight** forward for a desired distance, $d$.
The encoder counts, $C$, on both motors will increase to a targeted value, synchronously.
Please write down an equation for calculating the target encoder counts $C$, given the desired linear travel distance, $d$.
You can use following definitions in your equation:

- Wheel radius: $r$
- Gear ratio: $i$
- Encoder's counts per revolution: $CPR$

> [!TIP]
> If other quantities than the listed ones are needed.
> Please introduce them in math language.

#### 1.2. Encoder Guided Angular Motion

Assume your robot will spin around the center of the wheel axle for a desired angle, $\theta$.
The encoder counts on left motor, $C_l$, and the encoder counts on right motor $C_r$, will change synchronously, but in opposite directions.
Please write down one equation or two for calculating the targeted encoder counts, $C_l$ and $C_r$, given the desired spinning angle, $\theta$.
You can use following definitions in your equation:

- Wheel axle length: $L$
- Wheel radius: $r$
- Gear ratio: $i$
- Encoder's counts per revolution: $CPR$

> [!TIP]
> You may find the calculation of arc length as illustrated below helpful.
> ![arc_length](images/arc-length-formula.png)

### 2. Coding

**Please upload all customized python module or template scripts (e.g. `sensored_motor_driver.py`)**

   Initially, place the robot's driving wheel axle center (**AC**) right on top of the starting point (`checkpoint 4`). Align the robot's heading direction to point `checkpoint 1`

   1. (15%) Let the robot follow the trail from `checkpoint 4` to `checkpoint 1`. Based on the encoder feedback and calculation, stop the robot when **AC** is less than 0.05 m to the `checkpoint 1` (**the closer the better**).
   2. (5%) Measure and log the distance from **AC** to the `checkpoint 1` here:  
   3. (15%) Resume driving, let the robot follow the trail from `checkpoint 1` to `checkpoint 2`. Based on the encoder feedback and calculation, stop the robot when **AC** is less than 0.1 m to the `checkpoint 2` (**the closer the better**).
   4. (5%) Measure and log the distance from **AC** to the `checkpoint 2` here:  
   5. (15%) Resume driving, let the robot follow the trail from `checkpoint 2` to `checkpoint 3`. Based on the encoder feedback and calculation, stop the robot when **AC** is less than 0.15 m to the `checkpoint 3` (**the closer the better**).
   6. (5%) Measure and log the distance from **AC** to the `checkpoint 3` here:  
   7. (15%) Resume the driving, let the robot follow the trail from `checkpoint 3` to `checkpoint 4`. Based on the encoder feedback and calculation, stop the robot when **AC** is less than 0.2 m to the `checkpoint 4` (**the closer the better**).
   8. (5%) Measure and log the distance from **AC** to the `checkpoint 4` here:  

> Hint:
>
> 1. Wanna drive your robot straight? Read encoder counts on both motors and compare them to regulate motors' on/off states.
> 2. Turn at a certain angle: $s = r \cdot \theta$, where $s$ is the arc length in **meters**, $r$ is half of the wheel separation distance in **meters**, $\theta$ is the turning angle in **radians**.

### 2 (20%) Upload a video which records the entire navigation process

You'll want to modify lines in your [code](trail_follow.py) to reduce the stop time on each checkpoint.
