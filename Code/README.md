

This folder consists of 3 main code files containing codes in which the first file - 'Sound_source_navigation.ipynb' consists of the simulation and algorithms code, the second file - 'IMU.ipynb' consists of my attempts to work on the IMU data and the third file - 'Lidar_PointCloud.ipynb' consists of the basic analysis of the point cloud data that I created before researching ways to work with it.

The simulation and associated algorithm code (Sound_source_navigation.ipynb):

In this code the input involves creating a floor plan to test the algorithm on. For this a class called the 'build_matrix' was created. The functions in this class allow to create an initial rectangular room by giving length and breadth, closed rectangular obstacles within the room by giving diagonally opposite coordinate values, and independent walls by giving start and end coordinate points of the wall. By breaking down the floor plan into each of these components and giving the corresponding values we can test various cases.
The source and receiver values can be randomised or given specific coordinate values using the corresponding functions in the same class.
The variable 'distance_factor' can be modified to change the value of maximum edge length and line of sight distance. These can also be individually changed by going to the corresponding function default parameters.
The variable 'distance_limit' gives the distance at which the light rays attenuate in our simulation.
The variable 'lidar_range' gives the distance limit until which we consider the lidar to be able to detect the point cloud.

By giving these values at the appropriate places (comment of where floor plan creation starts and ends is mentioned in the file) and running the rest of the code as it is will allow different floor plans to be tested. 
The entire code gives the graph generated and path followed by blind search and selective search algorithms as well an estimate of the time taken in each case.
At the end there are 2 functions called 'cdf_time' and 'cdf_time_selective'. These functions take parameters which are the created floor plan and number of times to be run and then randomizes the source and receiver to generate that amount of cases. A cdf of this data is generated.

Comments: 

For the most part, this code is robust however as mentioned in the report there are a few issues. There seems to be an issue in ray reflections part of the code where the ray is reflecting in the wrong direction.
The code also fails when the receiver is too close to walls and unless distance parameters are adjusted, graph is not generated properly.

IMU code (IMU.ipynb):

This code consists of 3 algorithms:

The first is my attempt at PDR but this was not effective and gave faulty results. I think the issue might be related to calibrating the z-component of the angular acceleration to make sure that the orientation of the device is taken into account. 

The second algorithm I modified from "https://github.com/pajaraca/IEZ" but this isnt giving accurate results either. 

The third algorithm I started writing involves the step counting and smoothing approach to pdr but this wasnt completed. 

I have included 2 files 'IMU_outpu11.txt' and 'IMU_output2'.txt which are data from the IMU. To run this code the file name for the varible fi must be changed to appropriate value.
In the secong algorithm the 'acc_factor' and 'gyro_factor' parameters can be tweaked to give accurate results. I was not able to figure out the correlation properly which was why it was not working.

LiDAR code (Lidar_PointCloud.ipynb):

This code consists only of the analysis of the point cloud data that I wrote. It shows the data received in plotted form.

I have included the LiDAR data in the lidar_pcl folder and to run this file for any of the data the path in the variable 'file' in the code must be modified appropriately.


Additional code file (Sound_source_navigation_WIP.ipynb):

This file is similar to the first file but it consists of modifications I made to some funtions to incorporate the hardware into the algorithm. i.e. I started writing functions to take the hardware input and work accordingly. But this was not complete and I am attaching the file for your reference.



