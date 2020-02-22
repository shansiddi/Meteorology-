# CTD
Shan Siddiqui<br />
Dr. Abadi<br />
B ME 450<br />
2/21/20<br />
<p align="center">
<b>Code Link: https://github.com/shansiddi/Meteorology-/blob/master/main.ipynb</b><br>

<b>Introduction</b><br>

The latest year of data was downloaded from the OOI of Oregon Shelf Surface Mooring and Oregon Offshore Surface Mooring [1]. The bulk meterology instrument package was selected. The bulk meterology instrument package characterizes weather conditions above the sea surface. Wind speed and rain rate were analyzed over the course of a year for the two locations. Oregon shelf surface mooring was at 44.6393 degrees North and 124.304 degrees West. Oregon offshore surface mooring was at 44.3811 degrees North and 124.956 degrees West. The distance between the two sites was 59.14 kilometers. 

Problem 1) For each site, plot wind speed (in m/s) and rain rate (in mm/hr) Find these time windows: when it is windy and rainy, when it is rainy but not windy, when it is windy but not rainy, when it is not windy not rainy. Show each time period on 
your plot (for example, use different colors and have a legend to show which region each color represents)

Problem 2) Plot the cross-correlation function between wind speed at both sites. What is the highest correlation? What is the time lag?

Problem 3) Plot the cross-correlation function between rain at both sites. What is the highest correlation? What is the time lag?

Problem 4) Is there any relationship between the time lag of wind speed and rain rate? 

Problem 5) In another plot, calculate and plot the monthly average of the wind speed and rain rate
for each site
What pattern do you see? Explain.
Which month had the highest rain rate? 
Which month had the lowest rain rate?
Which month had the highest wind speed?
Which month had the lowest wind speed?

<b>Methods</b><br>

Python scripts in Jupyter Notebook were written to address the problems. See link at top of readme for complete code.

Method 1) Data was loaded into the environment via OOI's M@M interface. Time, rain rate, and wind speed were pulled from the data source and sorted. Time was converted to datetime. Data was split into the following cases when it is windy and rainy, when it is rainy but not windy, when it is windy but not rainy, when it is not windy not rainy. Rain rate and wind speed were plotted on a scatter plot. Cases were represented with axvspan which draws color bars in the background of the plot.

Method 2) np.correlate was used to compute covariance of the data at the Oregon shore and offshore wind. After computing correlation, with the covariance and standard deviation of the two sets; correlation was plotted against lags. The method for computing calculation was found from the University of Hawaii [2].

Method 3) np.correlate was used to compute covariance of the data at the Oregon shore and offshore rain. After computing correlation, with the covariance and standard deviation of the two sets; correlation was plotted against lags. The method for computing calculation was found from the University of Hawaii [2].

Method 4) To find a relationship between time lag of wind speed and rain rate at the two lags were compared. The distance between the two instruments was factored in to guage wind speed. Visual data of wind from EarthWindMap was considered to ground relationships against another source of data [3].

Method 5) An averaging function was used to first split the data into months then find monthly averages. Average data was plotted for each site and analyzed.

<b>Results</b><br>

Results 1) 

![](images/fig1.png)
<p align="center">
<b>figure 1: Rain Rate and Wind Versus Time for Both Sites</b><br>
  
Results 2)

![](images/fig2.png)
<p align="center">
<b>figure 2: Wind Correlation</b><br>
  
Results 3)

![](images/fig3.png)
<p align="center">
<b>figure 3: Rain Rate Correlation</b><br>
  
Results 4)

![](images/fig4.png)
<p align="center">
<b>figure 4: Lags of Wind and Rain</b><br>
  
![](images/fig5.png)
<p align="center">
<b>figure 5: Vector Map Shelf[3]</b><br>
  
![](images/fig6.png)
<p align="center">
<b>figure 6: Vector Map Offshore[3]</b><br>  
  
Results 5)

![](images/fig7.png)
<p align="center">
<b>figure 7: Monthly Averages [3]</b><br>


References

[1] NSF Ocean Observatories Initiative Data Portal, http://ooinet.oceanobservatories.org. Downloaded on (2/21/20).

[2] “Correlation¶,” SEM_EDOF. [Online]. Available: https://currents.soest.hawaii.edu/ocn_data_analysis/_static/SEM_EDOF.html. [Accessed: 21-Feb-2020].

[3] C. Beccario, “a global map of wind, weather, and ocean conditions,” earth. [Online]. Available: https://earth.nullschool.net/. [Accessed: 21-Feb-2020].
