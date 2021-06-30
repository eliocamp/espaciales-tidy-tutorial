---
title: blabla
---

Tutorial title
R Spatial without frameworks 


Description
Provide a paragraph with topics to be covered also mention a brief detail of resources to deliver the tutorial online using active teaching (e.g., break out rooms?, pair programming? shared repo?) - 2500 characters

In this tutorial we will learn how to download, read, analyse and visualise gridded spatial data within R using tidy data principles. 

This will be a completely hands-on tutorial with live coding and short exercises throughout the workshop. These exercises will include faded examples, code debugging, asking participants to predict code output. There will be time to work in groups (using breakout rooms) so that participants can answer their own questions about the data by writing their own code. At the end there will be time for Q&A. 

By the end of the workshop, participants will have written code with all the steps in the data analysis process (download data, read in memory, transform it, and visualise it) using the packages and functions they learned during the workshop. 

Participants will be asked to install the necessary packages and create the necessary login credentials to access public climate data. There will be a public instance of RStudio Cloud set up for those who had installation problems. Materials will be available in a public repository.






motivation
Why is tutorial suitable for participants of useR! 2021 ? - 2500 characters


Provide a tutorial outline with the approximate duration of each section, example: lecture 20 minutes, live coding 15 minutes, lab 20 minutes. 2500 characters

10 Introductory Lecture
40 live coding with short exercises

5 Pause

50 Live coding with short exercises

5 Pause

30 Live coding with short exercises
30 Breakout rooms work

10 Questions (and answers)



Learning Goals and Objectives .
Provide a paragraph or list of learning goals and objectives - 2500 characters

- Apply the concept of tidy data to gridded spatial data. 
- Download gridded data from climate models and reanalysis from Climate Data Store programmatically. 
- Read gridded data from NetCDF files, including subsetting regions of interest.
- Apply statistical methods and transofrmations to gridded data using tidy data principles
- Visualise gridded data using ggplot2 and extension packages.




Keywords separated by commas. (minimum of 5 keywords)
ggplot2, spatial data, tidy data, meteorology, data visualization

S


Objetivos: 

- Aplicar el concepto de tidy data a datos espaciales grillados. 

- Leer netcdf en tidy, incluyendo hacer subsets. 

- Aplicarles métodos estadístcos. 

- Visualizar usando ggplot2 + amigos


Programa:

- What metR is and what it's not. 

- Tidy data
	- raster tidy

- Climate Data Store
	- Setting an account with ecmwfr 
	- Creating a request with addin and downloading data. 

- ReadNetCDF
	- Glance
	- Subset
	- using DAP

- Operations
	- FitLm
	- EOF
	- widyr::pairwise_cor


- Visualisation
	- geoms
	- scales
    - ggperiodic
    - ggnewscale
    - gganimate


Outline:

10 Introductory Lecture
40 live coding with short exercises

5 Pause

50 Live coding with short exercises

5 Pause

30 Live coding with short exercises
20 Time for questions. 


