# AI-Fitness-Coach
Correction and Estimation of Workout Postures using Pose Estimation With OpenCV

During exercise, maintaining good posture is important. Incorrect posture can lead to ineffective workouts and health complications. The model analyzes the workout exercises by tracking the body angles derived from the changes in the body forms. A very useful visual analytical tool to enable safe physical exercises.

We examine at workout videos and evaluate the posture of the individual performing the activity on a scale of 0 to 1. We may make this procedure easier by using the following methodology :

1. Frame-by-frame analysis of videos (for high fps videos we can analyze every X frames since frames will be very repetitive and tune X accordingly to satisfy our needs). The OpenCV object VideoWriter will be used. For each frame we score the exercise posture.

2. First, we feed our image into the OpenPose keypoint detection model for human posture identification (which has been pre-trained with over 40 000 samples using the MPII dataset). This provides us with the positions of particular joints (right shoulder, left elbow, and so on), which we can then feed into a classification algorithm to determine whether or not the exercise performance is in proper posture.

3. Our classification step involves using a machine learning model to classify the posture of the individual performing the exercise. Ridge Regression Ensemble was used for deployment and results justify that it seemed to be the best performing model. 

4. Finally, we take each posture score and print this information onto the frame of the video and write each frame to our output object.

Output of this Code :
https://github.com/Rushikesh042/AI-Fitness-Coach/blob/main/testing_data/output.mp4


References :
[1] https://github.com/spmallick/learnopencv
[2] https://github.com/wangzheallen/awesome-human-pose-estimation
