# Documentation
A collection of notebooks documenting data team processes, tools, and known issues.

Work on this repo is in progress. Some notebooks may not be in a final state. Others are still being added.

## Content

#### Data Access and Plotting Notebooks
* Access, plot, and work with various data types.  

#### Metadata Access Notebooks 
* Request asset deployment information.  
* Request calibration values.  
* Parse automated QC data quality algorithm test results.  
* Request annotations. 
* Using annotations and qc values to filter out questionable data.  

#### Quality Control Notebooks
* Examples of OOI data QC workflows and reports in notebook form.

#### Known Issues Notebooks
* Wherever applicable, known issues are mentioned in context of the notebooks, but also reiterated here.
* Other known high-level issues and Redmine summaries are provide here.

<!-- #### Science Notebooks -->


## Running Notebooks in the Cloud
To run the notebooks in the cloud via the free mybinder.org service funded by the Moore Foundation, click here: [![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/ooi-data-review/ooi_datateam_notebooks/master)

The processing power of this free service is limited, so the high data volume examples may run slow. It is recommended to run these on your local machine by cloning this repository. See Local Setup instructions below. Another alternative to run high data volume examples is via the commercial cloud. For example, you can deploy a [pangeo](https://github.com/pangeo-data/pangeo) instance with free credits from any of the commercial cloud providers.  

## Local Setup

If you are not using the mybinder instance or above, you can run these notebooks on your local machine as well. To do so:    

Clone this repository to your local machine.  
```
$ git clone https://github.com/ooi-data-review/ooi_datateam_notebooks.git
```

Download and install [miniconda](https://conda.io/miniconda.html), then add the conda-forge channel.
```
$ conda config --add channels conda-forge
```

Create an environment, called ooi, for example.
```
$ conda create -n ooi python=3 jupyter ipykernel requests xarray dask netcdf4 pandas numpy matplotlib bokeh cmocean
```

Activate your new environment and install wget
```
$ source activate ooi
```

Add the ooi environment to jupyter as a selectable kernel for your user.
```
$ python -m ipykernel install --user --name ooi
```

Launch the local notebook server
```
$ jupyter notebook
```

## Other useful repositories to know about


### OOI Local Data Processing
This repository contains code that can be used to process data from raw to final data produce on your local machine, but using OOI open source algorithms and data parsing routines.  
https://github.com/ooi-data-review/ooi_local_processing


### Data Team QC Database
This repository contains the code that is used to produce the OOI Data Team QC Database website (visualocean.net). This website consolidates and organizes information about the OOI CI system to aid with data evaluation. It also visualizes data availability statistics at a daily resolution.  
https://github.com/seagrinch/data-team-portal


### Data Team OOI Stats and Alerts Scripts
This repository contains the code used to produce the data availability statistics seen at visualiocean.net. It also contains code that checks all parameters in the system against global range values and produces a binary pass/fail output at a daily resolution. This has not yet been visualized at visualiocean.net. Finally, it also contains code that sends out daily alerts on data availability and global range pass/fail results for all parameters in the system, as well as platform engineering data. The list of recipients is not currently subscribable and is hard coded into the routine running on a cron job on Rutgers Rutgers Department of Marine and Coastal servers.  
https://github.com/ooi-data-review/ooi_stats/

### OOI M2M Client Library
This repository contains code that can be used to send bulk requests for data from the OOI system.  
https://github.com/kerfoot/uframe-m2m


## Authors and Contributors

<!-- #### Principal Investigators
> Scott Glenn
Oscar Schofield -->

#### Management
> Michael Crowley  
Michael Vardaro  

#### Data Evaluation
> Leila Belabbassi  
Lori Garzio  
Friedrich Knuth  
Michael Smith  

#### Programming and Data Architecture
> John Kerfoot  
Sage Lichtenwalner  

### About the OOI Data Team

The mission of the OOI Data Team at Rutgers University is to facilitate access to quality-controlled and annotated OOI datasets. We encourage researchers to collaborate through the use of these real-time, concurrent, and interdisciplinary measurements, in the exploration of short-lived events, as well as long-term trends in ocean systems.

#### Contact
Email: help@oceanobservatories.org

#### TODO
* add notebook on retrieving and working with ooi shipboard data
* include overview of status on shipboard data under known issues
* add lines to request a count of all annotations in the system to annotations notebook
* add example of using annotations and qc values to filter out questionable data
* add notebook on parsing Redmine for known issue entered by the data team
* add notebook on how to request and download data from multiple instruments


