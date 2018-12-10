Indicator function for optical flow estimations 
===================================================

Image-based velocimetry techniques have captured great interest in the laboratory study of air-water flows, for example bubble image velocimetry (BIV) or optical flow (OF). Because recorded video sequences in air-water flows are often subject to image noise, a new filtering technique is proposed. This indicator function relies on the image gradient magnitude and works directly on the image plane, including the following benefits: 

- Removal of erroneous data.
- Filtering of foreground movement.
- Filtering of air-water interfaces.

Overall, the uploaded source code allows computation velocity fiedls in air-water flows using the Farnebäck method  ([handle](https://www.ida.liu.se/ext/WITAS-ev/Computer_Vision_Technologies/PaperInfo/farneback02.html)). If using the uploaded files for publishing research, please cite the following reference to credit the authors and to direct readers to the original research work:

M. Kramer and H. Chanson (2019). Optical flow estimations in aerated spillway flows: Filtering and discussion on
sampling parameters, Experimental and Thermal Fluid Science ([DOI](https://doi.org/10.1016/j.expthermflusci.2018.12.002))


1 Contents
----------
The code is written in Matlab R2017a. This repository contains source code files and a represetative spillway data set:
- RunIF.m: main code to run the optical flow estimations with indicator function.
- spillway-data: short video sequence of the air-water flow down a stepped spillway, recorded with a phantom v2011 high-speed video camera.


2 Processing parameters
------------------------
Important processing paramters of the OF technique are:

3 How to run the code?
----------------------
Copy the source code and the *.avi file into the same folder and run "RunIF.m". Instantaneous velocities are accessible through the Matlab workspace and time-averaged results will be saved to an Excel spreadsheet.

4 Comment on measurement accuracy
----------------------------------
Phase-detection probe measurements may overestimate time-averaged velocities and underestimate turbulence intensities, as shown in     Corre and Ishii (2002, [DOI](https://doi.org/10.1016/S0029-5493(02)00130-9)) and Kramer et al. (2019). Possible reasons include:
- Probe tips are not aligned with flow streamlines.
- A greater number of bubbles/droplets impact the tips during periods of high velocities. 

This topic is currently being investigated. It is anticipated that the measurement accuracy of a dual-tip probe decreases in two- or three-dimensional flow situations and in regions with high velocity fluctuations. 

5 Contact
----------
I am happy to receive **feedback**, **questions** and **recommendations** in the issue-section or via Email:

- Matthias Kramer, The University of Queensland, Brisbane, Australia. Email: m.kramer@uq.edu.au, [ORCID](https://orcid.org/0000-0001-5673-2751)

