Analysis of Fermi LAT data: Hands on session
==============================================

These are the tutorials for the hands on, practical session on the analysis of *Fermi* Large Area Telescope (aka LAT) gamma-ray observations for the [São Paulo School of Advanced Science on High Energy and Plasma Astrophysics in the CTA Era](http://www.astro.iag.usp.br/~highenastro/). The goal of this activity is to get you started on the analysis of Fermi LAT data while giving you a concrete overview of the steps involved. 

This activity has a total duration of 4 hours distributed in two days. Given the somewhat short duration of these sessions, we will not have time to get into the details of all the fascinating science behind the analysis. The emphasis is on “getting your hands dirty” with the data. 

- [Pre-requisites](./tutorials/pre-requisites.md), including instructions for [downloading](./tutorials/pre-requisites.md#download-links) and [installing](./tutorials/pre-requisites.md#instructions-for-installing-vm) the VM
- [Tutorials](#tutorials)
- [Solutions](#solutions)
- [Repository layout](#repository-layout)
- [Contact](#contact)


# Tutorials

## Day one

- 4:30-5:00: Introduction, overview of activities and tools: [slides (PDF)](./slides/day01-intro_slides.pdf), [Speaker Deck](https://speakerdeck.com/rsnemmen/analysis-of-fermi-lat-data-hands-on-day-1)
- 5:00-5:30: [Obtaining and preparing LAT data for your favorite source](./tutorials/prepare.md)
- 5:30-6:30: [Exploring LAT data: Plotting the counts map](./tutorials/explore.md)

## Day two

- 4:30-5:00: Overview of activity, basic theory of spectral modeling: [slides (PDF)](./slides/day02-intro_slides.pdf), [Speaker Deck](https://speakerdeck.com/rsnemmen/analysis-of-fermi-lat-data-day-2), [jupyter notebook](./notebooks/fermi_likelihood_lecture.ipynb)
- 5:00-5:30: [Getting a flux: Likelihood analysis](./tutorials/likelihood.md)
- 5:30-6:30: [Creating a spectrum (SED)](./tutorials/sed.md)
- Bonus: [Producing a light-curve](./tutorials/lc.md)
- [Concluding slides (PDF)](./slides/conclusion.pdf)

# Solutions

- [Obtaining and preparing LAT data](./solutions/prepare-solutions.md)
- [Exploring LAT data](./solutions/explore-solutions.md)
- [Likelihood lecture notebook](./solutions/fermi_likelihood_lecture-solutions.ipynb)
- [Likelihood analysis](./solutions/likelihood-solutions.md)
- [Creating a spectrum (SED)](./solutions/sed-solutions.md)

# Repository layout

| Folder | Contents |
| --- | --- |
| [slides/](./slides/) | Introduction and concluding slides in PDF format |
| [tutorials/](./tutorials/) | Pre-requisites and hands-on lessons |
| [notebooks/](./notebooks/) | Student lecture notebooks |
| [solutions/](./solutions/) | Exercise solutions, including the solutions notebook |
| [examples/](./examples/) | Sample configuration and analysis output |
| [figures/](./figures/) | Images shared by the tutorials, notebooks, and solutions |

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
