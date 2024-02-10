Set up a ground vehicle(car) with GPS, IMU(with sensor fusion) and LIDAR on the ROS Noetic platform.
Achieved improvements in SLAM loop closure, detection of dataset points and accuracy by aligning IMU with LIDAR odometry.

# Problems faced
-> LeGO LOAM mapped some objects, like trees, twice because there is no loop closure
-> In the absence of loop closure, it couldn’t perform corrections when the car went back to a place it had already mapped
-> This is the reason the sensor sweeps are not overlapping and a continuous drift is occurring as observed in the image
-> This can be avoided by including loop closure algorithms with the existing LEGO-LOAM algorithm
<img src="https://github.com/mescaline116/LiDAR-SLAM-using-LeGO-LOAM/assets/71351959/c291d80f-c4de-47ef-966f-cca82cdb6c90" arg="unnamed" width=300 height=200>
# IMU Integration
->When the odometry is obtained by using only the LiDAR point cloud data the map generated is moving out of the plane.
->The IMU data is used map optimization and feature association in LEGO-LOAM.
->By adding the IMU data there is clear improvement in the resultant map. This can be observed in the images demonstrated.
## Map without IMU i/p:
<img src="https://github.com/mescaline116/LiDAR-SLAM-using-LeGO-LOAM/assets/71351959/098f9ea7-f4a7-4064-b5aa-127652c128c4" arg="unnamed (1)" width=300 height=200>

## Map with IMU i/p:
<img src="https://github.com/mescaline116/LiDAR-SLAM-using-LeGO-LOAM/assets/71351959/5b316b46-b849-4179-b917-3eac94de6805" arg="unnamed (2)" width=300 height=200>



