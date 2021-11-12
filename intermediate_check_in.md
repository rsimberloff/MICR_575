Intermediate check-in
================

**[Link to final project
repository](https://github.com/rsimberloff/MICR_575_final_project)**  
*I made this repo private because it will include unpublished results
and I didn’t want to worry any of my coauthors. I added you as a
collaborator, which I think will allow you to see it. Let me know if
this doesn’t work!*

My final project is an analysis of location data from white-crowned
sparrows in the San Francisco Bay Area, and expands upon work done for
my Master’s thesis.

**This project will include:**

-   calculation of the territory area of each focal male (via kernel
    density estimation, potentially with a movement-based kernel)  
-   visualization of sparrow territories  
-   evaluation of my sample size (i.e. are 90 locations sufficient for
    accurate home range estimation?)  
-   statistical analysis of what may drive variation in territory area,
    including likely explanatory variables such as age, background
    noise, habitat type (urban/rural), and background noise  
-   visualization of statistical results  
-   written introduction, methods, and discussion  
    All these elements will be included in a markdown document.

**Progress, as of November 11**

Completed:

-   I have successfully calculated territory areas using the package
    `adehabitatHR`.  
-   I have saved the territory polygons (95% & 75% utilization home
    range contours) as shape files, the first step toward
    visualization.  
-   I have run some exploratory statistical analyses. Though not
    formalized (I need to think more about my model parameters), it
    appears that background noise predicts territory size! Hooray!

In progress:

-   Writing is underway (currently in a Word doc, as that’s more
    comfortable for drafting text than .Rmd)  
-   I am working on evaluating my sample size, for which I need to take
    repeated random samples of my location data from each bird at
    increasing sample sizes (e.g. 50 samples of 10 locations, 50 samples
    of 20 locations, 50 samples of 30 locations, etc.) to test whether
    the territory area appears to plateau (good – 90 locations is
    sufficient) or continues to increase with increasing locations (bad
    – 90 locations is insufficient). Tragically, I can’t figure out a
    way to do this without a `for()` loop. Nevertheless, I think I’m
    making progress.
