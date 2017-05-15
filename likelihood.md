Likelihood analysis: create sed for PG1553, reproducing old result from collaboration
============================

test installation: `enrico_setupcheck`


same activity as the MP school

# get data

data extracted using the following parameters:
![](./figures/pg1553_query.png)

15 deg radius

available in directory `day02/data`

# Create a configuration file

open terminal

```shell
cd day02
mkdir spectrum
cd spectrum
```

Parameters below from http://fermi-hero.readthedocs.io/en/latest/spectrum/index.html#make-a-config-file
z=0.36

create config file:

```
[fermi@localhost spectrum]$ enrico_config pg1553.conf
[Message]: Please provide the following required options [default] :
Output directory [/home/fermi/day02/spectrum] : 
Target Name : PG1553  
Right Ascension: 238.93
Declination: 11.19
redshift, no effect if null [0] : 0.36
ebl model to used
0=Kneiske, 1=Primack05, 2=Kneiske_HighUV, 3=Stecker05, 4=Franceschini, 5=Finke, 6=Gilmore : 0
Options are : PowerLaw, PowerLaw2, LogParabola, PLExpCutoff, Generic
Generic is design to allow the user to fit with non-supported models
EBL absorption can be added for PowerLaw2, LogParabola, PLExpCutoff
Spectral Model [PowerLaw] : PowerLaw2
ROI Size [15] : 
FT2 file [/home/fermi/enrico/Data/download/lat_spacecraft_merged.fits] : /home/fermi/day02/data/pg1553_SC00.fits
FT1 list of files [/home/fermi/enrico/Data/download/events.lis] : events.txt
tag [LAT_Analysis] : spectrum
Start time [239557418] : 
End time [334165418] : 
Emin [100] : 
Emax [300000] : 
IRFs [CALDB] : 
evclass [128] : 
evtype [3] : 
Corresponding IRFs	=	('P8R2_SOURCE_V6', ['BACK', 'FRONT'])
Is this ok? [y] : 
Corresponding zmax =  90
```


# create XML (what this means for the analysis)

create XML:

```
[fermi@localhost spectrum]$ enrico_xml pg1553.conf 
use the default location of the catalog
use the default catalog
Use the catalog :  /home/fermi/enrico/Data/catalog/gll_psc_v16.fit
[Message]: Summary of the XML model generation
Add  41  sources in the ROI of  17.0 ( 15.0 + 2 ) degrees
4  sources have free parameters inside  3.0  degrees
0  source(s) is (are) extended
Iso model file  /home/fermi/enrico/Data/diffuse/iso_P8R2_SOURCE_V6_v06.txt
Galactic model file  /home/fermi/enrico/Data/diffuse/gll_iem_v06.fits
[Message]: write the Xml file in /home/fermi/day02/spectrum/PG1553_PowerLaw2_model.xml
``` 

# simple likelihood

enrico_sed pg1553.conf
this will take a long time
while it runs, go get some water
discuss Fermi science with your colleagues
...

on my computer: 
started 16:48
finished 17:45
1 hour!

Here is the [output from `enrico_sed`](./enrico_sed_output.txt).

while the analysis run...
explain all the tools that will be called

best-fit parameters

results file

## exercise: plot count maps, model map and residuals
is the fit good?
![](./figures/cmap,modelmap,residuals.png)
residuals look good?

## exercise
how to decide which model is better?

explain meaning of spectrum


