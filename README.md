Indicator function for optical flow estimations 
===================================================

Image-based velocimetry techniques have captured great interest in the laboratory study of air-water flows, for example bubble image velocimetry (BIV) or optical flow (OF). Because recorded video sequences in air-water flows are often subject to image noise, a new filtering technique is proposed. This indicator function relies on the image gradient magnitude and works directly on the image plane, including the following benefits: 

- Removal of erroneous data.
- Filtering of foreground movement.
- Filtering of air-water interfaces.

Overall, the uploaded source code allows computation velocity fiedls in air-water flows using the Farnebäck method. If using the uploaded files for publishing research, please cite the following reference to credit the authors and to direct readers to the original research work:

M. Kramer and H. Chanson (2019). Optical flow estimations in aerated spillway flows: Filtering and discussion on
sampling parameters, Experimental and Thermal Fluid Science ([DOI](https://doi.org/10.1016/j.expthermflusci.2018.12.002))


1 Contents
----------
The code is written in Matlab R2017a. This repository contains source code files and a represetative spillway data set:
- RunAWCCT.m: main code to run the AWCCT.
- chord.m: evaluation of chord times.
- roc.m: robust outlier cutoff. Simplification of Goring and Nikora (2002, [DOI](https://doi.org/10.1061/(ASCE)0733-9429(2002)128:1(117))), as modified by Wahl (2003, [DOI](https://doi.org/10.1061/(ASCE)0733-9429(2003)129:6(484))). ROC only uses instantaneous velocity data (instead of gradients). Note that velocity series are sparse in time, thus gradients correspond to different dt. Further description in Valero (2018, [handle](https://orbi.uliege.be/handle/2268/229191)).
- thres.m: single threshold technique and void fraction calculation.
- velocity.m: computation of pseudo-instantaneous velocities. 
- windows.m: segmentation of the signal into short time windows.
- spillway-data: phase-detection probe data, measured at the eighth step edge of a large-sized stepped spillway, see Kramer et al. (2019).


2 Processing parameters
------------------------
Important processing paramters of the OF technique are:
- **N<sub>P</sub>**: number of encompassed particles of the dispersed phase. For example, a window with 
N<sub>P</sub> = 2 particles contains two water chords and two air chords, compare Fig. 1 in Kramer et al. (2019). A value between N<sub>P</sub>  = 2 and 5 was used for synthetic and real two-phase flow signals. 
- **R<sub>12,max</sub>**: threshold of the maximum cross-correlation coefficient. A value between R<sub>12,max</sub> = 0.5 to 0.7 is recommended, compare Matos et al. (2002, [DOI](https://doi.org/10.1061/40655(2002)58)) and André et al. (2003, [DOI](https://doi.org/10.1061/(ASCE)0733-9429(2005)131:5(423))). 
- **SPR**: threshold of the secondary peak ratio, as defined in Kramer et al. (2019). In accordance with Keane and Adrian (1990, [DOI](https://doi.org/10.1088/0957-0233/1/11/013)) and Hain and Kähler (2007, [DOI](https://doi.org/10.1007/s00348-007-0266-6)), a value of SPR = 0.6 is proposed.

3 How to run the code?
----------------------
Copy the source code and the *.dat files into the same folder and run "RunAWCCT.m". Instantaneous velocities are accessible through the Matlab workspace and time-averaged results will be saved to an Excel spreadsheet.

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

