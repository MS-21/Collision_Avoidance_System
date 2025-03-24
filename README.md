# Collision_Avoidance_System

1. Data Processing Approach
To develop an AI/ML-based obstacle detection system for Advanced Driver Assistance Systems (ADAS), we processed and analyzed data from radar and camera sensors. The key steps included:

Radar Data Preprocessing:

Loaded odometry data from radar_odometry.csv.

Computed vehicle movement trajectory by analyzing X, Y coordinates.

Derived speed by calculating the Euclidean distance between consecutive points.

Identified sudden movements to detect potential obstacles.

Camera Data Preprocessing:

Loaded images from the stereo camera dataset.

Applied object detection using the YOLOv10 model.

Extracted bounding box coordinates for detected objects.

2. Sensor Fusion Techniques Applied

Since LIDAR data was unavailable, we focused on Radar + Camera fusion using the following methods:

Time Synchronization: Mapped radar odometry timestamps to the closest available camera frames.

Data Association: Matched radar-detected motion changes with object detections in images.

Collision Prediction: Used radar speed calculations to predict high-risk obstacles.

3. Integration of Camera and Radar Data

The integration involved:

Detecting objects in the camera images using YOLOv10.

Mapping radar speed and trajectory data onto the detected objects.

Identifying whether detected obstacles were in the vehicle's path and determining potential collision scenarios.

4. Collision Avoidance Algorithm & Results

The implemented collision avoidance system:

Step 1: Compute vehicle movement trajectory and detect sudden speed changes.

Step 2: Detect objects in the vehicle’s path using YOLOv10.

Step 3: If an obstacle is present and sudden movement is detected, trigger warnings.

Step 4: Implement emergency braking or lane change recommendations.

Results:

The system successfully identified sudden braking instances.

When an obstacle was detected in the vehicle's path, emergency braking was triggered.

The algorithm issued alerts for potential collisions.
