# Comparison-of-Motion-Analysis-Systems
This repository contains data from the peer-reviewed manuscript titled "Comparison of Motion Analysis Systems in Tracking Upper Body Movement of Myoelectric Bypass Prosthesis Users" by Sophie Wang, Gene Civillico, Wesley Niswander, and Kimberly Kontson.  Full citation of the paper is below: Wang SL, Civillico G, Niswander W, Kontson KL. Comparison of Motion Analysis Systems in Tracking Upper Body Movement of Myoelectric Bypass Prosthesis Users. Sensors. 2022; 22(8):2953. https://doi.org/10.3390/s22082953

Raw joint angle data derived from three different motion analysis systems are provided in this repository.  Details on how to access and interpret the data (.MAT files) are provided below.  For further details on the analysis, we encourage you to read the above cited manuscript.

-------------------------------------------------------------

Within each joint angle MAT is a table where the rows are the tasks performed by all participants and the columns are the systems: "Vicon", "Kinect", "TrunVicon", "TrunXsens".

For a given task, all subject trials were interpolated to be the same size as the longest trial, so all trials within a task will be the same length.  

Due to computational errors, select trials were manually removed from the Xsens data to generate the "TrunXsens" dataset. To allow for the RMSE analysis, the Vicon data  was truncated to match the TrunXsens dataset by removing the same trials - resulting in the "TrunVicon" dataset. The "Kinect" dataset did not suffer from the same issues and did not need truncation, as such the "Kinect" and "Vicon" datasets have all 30 trials.

Within the SYSTEM columns are the 30 trials performed of each task, with columns 1:10 representing the 1st trial for particpants 1 - 10, respectively; columns 11:20 representing the 2nd trial for particpants 1 - 10, respectively; and columns 21:30 representing the 3rd trial for particpants 1 - 10, respectively. 

Each cell in the table represents a trial.  These cells are n x 3 matrices of angle data, where n represents the frame number of the time series trajectory and each column represents angle data for the last object interaction in the task. For example, you can isolate the Vicon right elbow angle data for the first subject's first trial performing the tBBT by using the syntax RElbowAnglesTrajStorage.Vicon{2,1}.  The joint angle degrees of freedom are specific to each joint MAT file, the joint angle data columns within each cell are as follows:

RELBOW MAT: Column 1 is Flexion/Extension, Column 2 is noise, Column 3 is noise

RSHOULDER MAT: Column 1 is Flexion/Extension, Column 2 is Abduction/Adduction, Column 3 is Internal/External Rotation

NECK MAT: Column 1 is Flexion, Column 2 is Lateral Flexion, Column 3 is Rotation

SPINE MAT: Column 1 is Flexion, Column 2 is Lateral Flexion, Column 3 is Rotation
