# ROS_ArUco_LGI
The ROS ArUco packages used in LGI experiments

To use this repository, it is necessary to firstly read all the instructions.
This repository is actually a bunch of known third-party packages that were merged in order to measure ArUco poses with an USB Camera attached to your computer. For this, it was used on Ubuntu 18.04.4 LTS and with ROS Melodic.

With this repository, you'll be allowed to use an USB camera to detect multiple ArUco markers visualize the image and see the poses outputs in real time via Linux terminal. Note: Depending on your USB camera, it uses a different image processing data, make sure your webcam is compatible with MJPEG. We used a Hp Hd-4110 13mp model. Other types of cameras were not tested, and therefore, some incompatibilities might occur.

To clone, you should go to your catkin_ws directory

$ cd catkin_ws/
$ cd src/
$ git clone 

Then, to compile using catkin_make:
$ cd .. 
$ catkin_make

Installation is now completed. Now, to launch, you have to edit some features to your personal PC.
First, you must have the camera calibration file. For this, go into a ROS camera calibration tutorial (http://wiki.ros.org/camera_calibration) and get this file. Then, replace it in ~/catkin_ws/src/marker_pose_detection/data.
After this, you should go to ~/catkin_ws/src/marker_pose_detection/launch/viewpoint_cam.launch and, in line 6, change your camera device.

Now to launch camera node and visualization:

$ roslaunch viewpoint_estimation viewpoint_estimation.launch viewpoint_cam.launch

And to see poses in real-time:

$ rosrun viewpoint_estimation distancia

This prints into the screen all the markers detected and their pose.
Currently we have a limited detection distance from 0.14 m to 2 m, so make sure your markers are placed in this interval.







