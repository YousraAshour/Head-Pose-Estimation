# Head-Pose-Estimation
Head Pose Estimation projects tries to predict the angles of face rotation in a 3D space through drawing the 3 position axis (pitch,yaw,roll) by predicting the 3 angels of each position. 
Dataset used is AFLW2000 dataset with contains 2000 image and 2000 matlab file with the 3 labels (angels). 
# Project Steps 
1. We will unzip the dataset file which contains the images and mat files each image has the same name with different extension (.jpg, .mat)
2. We will use MediaPipe library in training to get the face mesh (landmarks on the face) these will be used as features for training (936 column, 468 for X and 468 for Y) the result will be 1853 samples.
3. Then the angles are extracted from the mat file for each image and stored in separate arrays for each Pitch, Yaw and Roll.
4. Normalizing happens for the landmark points by setting a random point for all faces and subtracting all points from it then we calculate the euclidan distance between any two random points and divide each normalized point by it.
5. Then 3 regression models are chosen for Pitch, Yaw and Roll
6. The models are then tested on training and validation data and fine tunning is done.
7. For the testing face of new images the same steps happen including face mesh, normalization and predction of axis.
8. To test on a video or real time camera, a function is used to divide videos into frames, run the same steps on each frame separately and draw axis then refactor the frames into a video one more time.


