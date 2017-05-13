Solutions to exercises: Obtaining and preparing LAT data for your favorite source
=====================================================

## Exercise 1

This is one simple way of looping through the columns and printing them out:

```python
events=hdulist[1].data
n=events['ENERGY'].size # size of array

for i in range(n):
	print(i,events['ENERGY'][i], events['RA'][i], events['DEC'][i], events['TIME'][i])
```

## Exercise 2

```python
hist(events['ZENITH_ANGLE'],100)
xlabel('Zenith angle (degrees)')
```

![](./figures/plot_zenith_angle.png)



