THE ORIGINAL JUPYTER NOTEBOOK GIVEN IN THE GITHUB FOLDER WAS USED TO FILL THE CODE
PLEASE READ THE DETAILED COMMENTS IN THE CODE
THE WRITEUP.TXT IS A VERY BRIEF SUMMARY OF MY CODE

#PLEASE READ THE COMMENTS IN THE CODE

#THIS IS A SUMMARY OF WHAT MY CODE DOES


Libraries used: Numpy, Pandas, Matplotlib.pyplot, Astropy, Scipy

1. Imported data from the .csv file, cleansed it with the criteria mentioned in the jupyter notebook.(Removing the -99.990 V and I band entries)

2. The RA, DEC values were converted to degrees using astropy.coordinates.Skycoord
   The Period values are converted to seconds by multiplying with 86400 seconds/day

3. Plotted the RA, DEC coordinates in a sky grid using Matplotlib.pyplot. 
   Plotted the coordinates in all four builtin i.e, 'Hammer', 'Aitoff', 'Mollweide' and 'Lambert' projections.
   FOR MOLLWEIDE PROJECTION: Declared a 2D list `coord` in step 2 to store the RA and DEC values and use them later in HMS and DMS formats respectivly to plot the Mollweide projection.  

4. Plotted the band magnitude vs log(Period) graphs for both V and I band magnitudes.

5. Calculated the perpendicular distance from the points in the magnitude vs log(Period) graphs and used np.quantile to find and eliminate outliers below 5% and above 95%.

6. Binned the modified dataframe into 25 partitions based on 5 bins in RA and DEC values.

7. Used scipy.optimize.curve_fit to find the V band and I band intercepts for all the 25 partitions.

8. Found the deviation using the given formula : D_{V-I} = (GI_V - I_V) - (GI_I - I_I)

9. Plotted the histogram of D_V-I

10. Plotted the Wesenheit Index vs log(Period) graph using matplotlib
