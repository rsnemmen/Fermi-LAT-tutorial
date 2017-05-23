Generate a spectral energy distribution
======================================

Now you will learn how to produce a spectral energy distribution (aka SED) for the blazar PG 1553+113. A SED is simply a plot of flux or luminosity as a function of energy or wavelength. SEDs can teach you a lot about the physical processes responsible for the emission in the source. 

By following this tutorial, you will reproduce an [old result from the LAT collaboration](http://adsabs.harvard.edu/abs/2010ApJ...708.1310A). You will be able to compare the results of your analysis with those published in that paper.

In our [previous likelihood fit](./likelihood.md), we have obtained a fit of the source parameters to the global data (all energies and times) but we have not computed flux points to be plotted as a spectrum. To do so you have to run the analysis for each of the energy bins for which you want to generate a spectral point. If this sounds a bit complicated, this is because it is in fact a bit so. Fortunately, our friend `Enrico` can automate the SED-generation process!




# Copy files generated in the [previous activity](./likelihood.md)

First, let’s copy some files that we generated in the previous tutorial. In the terminal, type the following commands to create a directory that will hold the results from this analysis:

```shell
cd ~/LAT_day02
mkdir sed
cd sed
cp ~/flux/pg1553.conf ~/flux/events.txt . # copy previously generated conf. file and events list
```

# Customize configuration file

Let’s teach Enrico that it now needs to get SED points instead of doing only a global likelihood analysis. For this purpose, we need to change a few fields in the configuration file. Here are the instructions.

1. Open the configuration file `pg1553.conf` with a text editor.
2. Change only the following fields in the file:

`out = /home/fermi/LAT_day02/sed`   
(directory that will hold the output)

```
[file]
	event = events.txt
	xml = /home/fermi/LAT_day02/sed/PG1553_PowerLaw2_model.xml
	… 
```

```
[Ebin]
	NumEnergyBins = 7
	… 
```	
	

# Generate source model

You will generate now the XML file with the source model for your analysis:

    enrico_xml pg1553.conf 

# Compute SED points

You will use the `enrico_sed` tool again. This is how it works. It will first run a global fit and if the option `[Ebin] -> NumEnergyBins` in the configuration file is greater than 0. At the end of the overall fit `enrico` will run `NumEnergyBins` new analyses by dividing the energy range. Each analysis is a maximum likelihood fit run by the `enrico_sed` tool. If the TS found in any of the energy time bins is below `[Ebin] -> TSEnergyBins` then an upper limit is computed.

Now type in the terminal:

    enrico_sed pg1553.conf

You will need a very good patience now. It is unlikely that you will finish this analysis over the duration of the hands-on activity (unless you are a relative of The Flash). In my case, this analysis took about 3 hours running on a 2015 MacBook under the VM. Your patience will be rewarded.


# Plot the SED

Enrico will already have produced several diagnostic plots during the execution of the analysis tools. To plot the final spectrum, we will use the tool `enrico_plot_sed` which will use the results from the likelihood fitting to produce the SED plot. 

```
[fermi@localhost sed]$ enrico_plot_sed pg1553.conf 
[Message]: Save Ebin results in 
[Message]: Reading /home/fermi/day02/sed/Ebin7/PG1553_0.conf
[Message]: Energy bins results
Energy =  177.0
E**2. dN/dE =  1.08234529418e-11  +  1.8669187668e-12  -  1.8669187668e-12
[Message]: Reading /home/fermi/day02/sed/Ebin7/PG1553_1.conf
[Message]: Energy bins results
Energy =  556.0
E**2. dN/dE =  1.2966909576e-11  +  1.1563884279e-12  -  1.1563884279e-12
[Message]: Reading /home/fermi/day02/sed/Ebin7/PG1553_2.conf
[Message]: Energy bins results
Energy =  1745.0
E**2. dN/dE =  2.11215785539e-11  +  1.61963497302e-12  -  1.61963497302e-12
[Message]: Reading /home/fermi/day02/sed/Ebin7/PG1553_3.conf
[Message]: Energy bins results
Energy =  5477.0
E**2. dN/dE =  3.68410595707e-11  +  3.02001119251e-12  -  3.02001119251e-12
[Message]: Reading /home/fermi/day02/sed/Ebin7/PG1553_4.conf
[Message]: Energy bins results
Energy =  17190.0
E**2. dN/dE =  6.7988682993e-11  +  8.2282031554e-12  -  8.2282031554e-12
[Message]: Reading /home/fermi/day02/sed/Ebin7/PG1553_5.conf
[Message]: Energy bins results
Energy =  53954.0
E**2. dN/dE =  8.0641835618e-11  +  1.60158118073e-11  -  1.60158118073e-11
[Message]: Reading /home/fermi/day02/sed/Ebin7/PG1553_6.conf
[Message]: Energy bins results
Energy =  169338.0
E**2. dN/dE =  4.08989208649e-11  +  1.45252100068e-11  -  1.45252100068e-11
Info in <TCanvas::SaveSource>: C++ Macro file: /home/fermi/day02/sed/Spectrum/SED_PG1553_PowerLaw2.C has been generated
Info in <TCanvas::Print>: eps file /home/fermi/day02/sed/Spectrum/SED_PG1553_PowerLaw2.eps has been created
```

You should get the following plot as a result—which can be found in figure `./Spectrum/SED_PG1553_PowerLaw2.png`:
![](./figures/sed.png)

The redshift of this blazar is *z*=0.36. This turns out to be important. Because PG 1553 is relatively far away, gamma-rays will interact with lower energy photons in the [extragalactic background light (EBL)](https://www.universetoday.com/wp-content/uploads/hess_jet_quasar.jpg), pair-produce, and the resulting spectrum we will measure is not exactly a power-law but is attenuated at the high-energy end. This is the reason for the attenuation at energies >50 GeV. If you are curious about the EBL and its imprint on gamma-ray spectra, you should have a look at this very cool [*Science* paper published by the LAT Collaboration](https://www.dropbox.com/s/u0slge2wqwg5kca/ackermann2012.pdf?dl=0) ([try this if the previous link is broken](http://science.sciencemag.org/content/338/6111/1190/tab-pdf)).

## Exercise

Open the file `./Spectrum/SED_PG1553_PowerLaw2_CountsPlot.png` and inspect this plot. Notice the contribution of our dear blazar compared to all the other sources. Why do you think this count spectrum is different compared to the SED plot we saw before? (e.g. why is it not a perfect power-law extending to lower energies as we should expect?)