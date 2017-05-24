Generate a light curve 
======================================

In this hands-on activity, you will generate a light curve for the blazar 3C 279. 3C 279 is a violently variable blazar. It displays apparent superluminal motion. 

You will reproduce the gamma-ray flare observed with Fermi LAT in June 2015 and [reported in this paper](http://iopscience.iop.org/article/10.1088/2041-8205/808/2/L48/meta;jsessionid=755B23E02BBB464D1F754F551B848D23.c4.iopscience.cld.iop.org). We will use 

# Get the data

The data was extracted using the following parameters:
![](./figures/3c279_query.png)

These data spans about two weeks in the life of 3C 279. 

Normally you would go to go to the NASA FSSC server website, input the selection criteria and download the files. However, in order to save time and bandwidth, *all the necessary files have already been downloaded and are available in the VM* in the folder `LAT_day02/data`. The data files are the following:

- `3c279_PH00.fits`: events file
- `3c279_SC00.fits`: spacecraft file


# Initial setup

Let’s create the directory that will hold the results of your analysis:

```shell
cd ~/LAT_day02
mkdir lc
cd lc
```

You should download the configuration file that will be used to generate the light curve. The [configuration file is available to download here](./lc.conf).

## Exercise 1: Inspect the configuration file

Go ahead, open `lc.conf` in a text editor and inspect its content. Is the spectral index of the source free? How many temporal bins did we define to generate the light curve?

[comment]: <> (note the fixed spectral index at 2.0 like Paliya; 13 bins)


# Generate source model

You will generate now the XML file with the source model for your analysis:

    enrico_xml lc.conf


# Generate the light curve

We will use the `enrico_lc` tool to generate the light curve:

    enrico_lc lc.conf

Again, fasten your seat belts because this will take quite a long time to run. `enrico_lc` will first run a full likelihood fit for each time bin. In my 2015 laptop, this analysis took about 3 hours to finish.

# Plot the light curve

Now you will use the `enrico_plot_lc` tool to plot the resulting light curve:

    enrico_plot_lc lc.conf

## Exercise 2

Find the file `3C279_LC.png` which has the resulting light curve. Do you see a flare? 

Compare the light curve you just generated with Figure 1 in [Paliya 2015 ApJ](http://iopscience.iop.org/article/10.1088/2041-8205/808/2/L48/meta;jsessionid=755B23E02BBB464D1F754F551B848D23.c4.iopscience.cld.iop.org). Do they look similar?

## Exercise 3

Find the file `3C279_TS.png` which contains the time series of TS values. What is the peak statistical significance of the source over the period you considered? 