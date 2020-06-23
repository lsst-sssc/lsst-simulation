# LSST Simulation Issues
Repository to collect feedback/issues for the simulates SolSys Products DB


# Release notes SSPDB version 0.1

The SSPDB contains a full density simulation of Solar System Object observations during year one of the Legacy Survey of Space and Time (LSST) to be conducted at the Vera C. Rubin Observatory. 

## SSO Populations: 
S3M (Grav et al. 2011) 


## Survey Simulation: 
Operations Simulation (OpSim) run Feature Based Scheduler version 1.5 
http://astro-lsst-01.astro.washington.edu:8081/

## Observation Simulator: 
Naidu et al. (JPL)
https://github.com/AsteroidSurveySimulator/objectsInField

### Settings/features

* N-body propagation (perturbers: planets + Pluto/Charon)

* Actual LSST camera footprint (instead of statistical fill factor)

* Trailing losses

* “Fading”/statistical detection cutoff

* Observation uncertainties (RA, Dec, Filtermag)

* All SSOs have spectral types: S, C (Ivesić et al. 2001, Vereš & Chesley 2017)

* False detections: DIA & CCD noise (Jones et al. 2017, Vereš & Chesley 2017)


## Accessing SSPDB

SSSC Jupyter Hub:
https://sssc.dirac.institute

MySQL Database: 
db.dirac.institute (accessible from within JupyterHub only)



