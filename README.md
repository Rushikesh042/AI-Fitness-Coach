# AI-Fitness-Coach
Correction and Estimation of Workout Postures using Pose Estimation With OpenCV

During exercise, maintaining good posture is important. Incorrect posture can lead to ineffective workouts and health complications. The model analyzes the workout exercises by tracking the body angles derived from the changes in the body forms. A very useful visual analytical tool to enable safe physical exercises.

We examine at workout videos and evaluate the posture of the individual performing the activity on a scale of 0 to 1. We may make this procedure easier by using the following methodology :

1. Frame-by-frame analysis of videos (for high fps videos we can analyze every X frames since frames will be very repetitive and tune X accordingly to satisfy our needs). The OpenCV object VideoWriter will be used. For each frame we score the exercise posture.

2. First, we feed our image into the OpenPose keypoint detection model for human posture identification (which has been pre-trained with over 40 000 samples using the MPII dataset). This provides us with the positions of particular joints (right shoulder, left elbow, and so on), which we can then feed into a classification algorithm to determine whether or not the exercise performance is in proper posture.

3. Our classification step involves using a machine learning model to classify the posture of the individual performing the exercise. Ridge Regression Ensemble was used for deployment and results justify that it seemed to be the best performing model. 

4. Finally, we take each posture score and print this information onto the frame of the video and write each frame to our output object.

![output2](https://user-images.githubusercontent.com/54346227/139542449-efbee999-ef74-4c47-bb1e-811cae15bbd5.png)

![output](https://user-images.githubusercontent.com/54346227/139542443-cd160640-c005-4d10-a8ec-1daf8303c8d2.png)

https://user-images.githubusercontent.com/54346227/139542373-7effbc0c-9442-4148-9195-2570fdf1ae97.mp4

Built using pre-trained weights for OpenPose keypoint detection using the MPII pose estimation dataset, Python 3.8, OpenCV, Scikit-Learn and Jupyter Notebook.

PoseDetectionOpenCV.py : For Real Time Pose Estimation
PoseDetection_Notebook.ipynb : For User-Input Video based Pose Estimation

By getting the quantified data of a body motion, it is possible to find insights from the data. For example, hand speed can be calculated, angles between joints during the swing can be calculated as well. These data might be helpful for advanced training and maybe injury prevention.

References :
[1] https://github.com/spmallick/learnopencv
[2] https://github.com/wangzheallen/awesome-human-pose-estimation
