Analysis of Fermi LAT data: Day 1
=========================


I assume that you all already installed the VM and Virtual Box
overview of software that will be used: Science Tools and enrico
they are installed in the VM and ready to use

This thread leads you through extracting your LAT data files from the FSSC's databases. In order to analyze LAT data, you will need several LAT data products.
An events file containing the recorded events that correspond to your source of interest, as well as the area surrounding that source. The size of this surrounding "region-of-interest", or ROI, that you choose will depend on the density and brightness of nearby sources, as well as the type of analysis you are performing. There are two types of events files:
Photon Data - contains all information necessary for science analysis with SOURCE, CLEAN, ULTRACLEAN, or ULTRACLEANVETO event classes
Extended Data - contains all event data, including the standard Transient classes (TRANSIENT010 and TRANSIENT020), plus additional quantities produced by the Level 1 analysis
Only one type of event data file is needed to perform LAT science analysis. We recommend use of the photon data file for most purposes (except for the GRB analysis, for which the extended data are required). Event data for large datasets will be divided into multiple files. The next tutorial, Data Preparation, will discuss how to combine those files.
A spacecraft file containing spacecraft position and orientation information at 30 second intervals. This file is required for LAT science analysis. The LAT data server will only generate a single spacecraft file, regardless of the size of the dataset.
Some analyses also require models of the isotropic and Galactic diffuse background models. You can download them from the Background Models page.

Nice explanation of the analysis steps in the FermiPy tutorial

