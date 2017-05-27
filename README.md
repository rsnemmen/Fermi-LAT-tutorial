Analysis of Fermi LAT data: Hands on session
==============================================

These are the tutorials for the hands on, practical session on the analysis of *Fermi* Large Area Telescope (aka LAT) gamma-ray observations for the [São Paulo School of Advanced Science on High Energy and Plasma Astrophysics in the CTA Era](http://www.astro.iag.usp.br/~highenastro/). The goal of this activity is to get you started on the analysis of Fermi LAT data while giving you a concrete overview of the steps involved. 

This activity has a total duration of 4 hours distributed in two days. Given the somewhat short duration of these sessions, we will not have time to get into the details of all the fascinating science behind the analysis. The emphasis is on “getting your hands dirty” with the data. 

- [Pre-requisites](./pre-requisites.md), including instructions for [downloading](./pre-requisites.md#download-links) and [installing](./pre-requisites.md#instructions-for-installing-vm) the VM
- [Tutorials](#tutorials)
- [Contact](#contact)


# Tutorials

## Day one

- 4:30-5:00: [Introduction, overview of activities and tools (slides)](https://speakerdeck.com/rsnemmen/analysis-of-fermi-lat-data-hands-on-day-1)
- 5:00-5:30: [Obtaining and preparing LAT data for your favorite source](./prepare.md)
- 5:30-6:30: [Exploring LAT data: Plotting the counts map](./explore.md)

## Day two

- 4:30-5:00: Overview of activity, basic theory of spectral modeling: [slides](https://speakerdeck.com/rsnemmen/analysis-of-fermi-lat-data-day-2), [jupyter notebook](./fermi_likelihood_lecture.ipynb)
- 5:00-5:30: [Getting a flux: Likelihood analysis](./likelihood.md)
- 5:30-6:30: [Creating a spectrum (SED)](./sed.md)
- Bonus: [Producing a light-curve](./lc.md)

# Acknowledgements

- Luis Ricardo Manrique, Marco Antonio dos Santos: for general IT help, installing the VM on all flash drives and lab desktop machines, testing the VM
- [Fabio Cafardo, Raniere Menezes](https://rodrigonemmen.com/group/group-members/): for general brainstorming and helping with preparation of the tutorials
- LAT Collaboration, particularly Jeremy Perkins: for inspiration on the activities (very helpful [analysis threads](https://fermi.gsfc.nasa.gov/ssc/data/analysis/scitools/)) and the idea of the VM
- Christoph Deil and Victor Zabalza for [their nice tutorial](http://fermi-hero.readthedocs.io/en/latest/index.html#) which inspired parts of this one

# TODO (future)

- [ ] GRB tutorial
- [ ] reproducing the tentative dark matter line from the Galactic Center
- [x] upload data files required for activity on figshare

# Contact 

[`rodrigo.nemmen -> iag usp br`](http://rodrigonemmen.com/contact)

[Author's web page](https://rodrigonemmen.com/)

Twitter: [@nemmen](https://twitter.com/nemmen)