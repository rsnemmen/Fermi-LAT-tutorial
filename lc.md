create light curve for 3C 279, reproducing the Paliya et al. result
======================================

# get data

data extracted using the following parameters:
![](./figures/3c279_query.png)

data is already conveniently there

# Initial setup

cd ~/day02
mkdir lc
cd lc

use `lc.conf`
note the fixed spectral index at 2.0 like Paliya
13 bins

# Generate the light curve


enrico_xml lc.conf

enrico_lc lc.conf

