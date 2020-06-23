# LSST Simulation Issues
Repository to collect feedback/issues for the simulates SolSys Products DB.


# Release notes SSPDB version 0.1

The Solar System Products Data Base (SSPDB) contains a full density simulation of Solar System Object observations during year one of the Legacy Survey of Space and Time (LSST) to be conducted at the Vera C. Rubin Observatory. 
The aim of the SSPDB is to give the Solar System Science Collaboration (SSSC) a preview of what LSST data 
catalogs will look like. 
This first relase of the SSPDB is intended to serve as a testing ground during the LSST SSSC sprint 2020. Future updates of the SSSPDB will add fidelity and include additional data in order to provide as complete a mock catalog of LSST Solar System observations as possible.

## DB Realization
The SSPDB is currently realized as a MySQL database with three tables:

* DIASource
* MPCORB
* noise

The DIASource table contains information on individual observations of Solar System Objects (SSOs).
The MPCORB table contains orbit data for the SSO input populations.
The noise table contains false detections for every exposure. False detections are composed of Difference Image Artifacts (FD) and CCD Noise (NS).
 
Schemata have been implemented according to the following templates:
https://docs.google.com/spreadsheets/d/1E0rTlvuJC0CvpLNsuWLK0x70uhpZww4v6GB5QkiQr-Q

As of this moment several columns are empty or NULL. Those will be filled over the course of the upcoming SSPDB updates.

## Accessing the SSPDB
The SSPDB can be accessed via the SSSC Jupyter Hub @
https://sssc.dirac.institute


The MySQL data base is located @  
db.dirac.institute (accessible from within JupyterHub only)

## SSO Input Populations: 
Synthetic Solar System Model (S3M, Grav et al. 2011) 


## Survey Simulation
Operations Simulation (OpSim) run Feature Based Scheduler version 1.5 @ 
http://astro-lsst-01.astro.washington.edu:8081/

## Observation Simulator
Naidu et al. (JPL) @
https://github.com/AsteroidSurveySimulator/objectsInField

### Settings/features

* N-body orbit propagation (perturbers: planets + Pluto/Charon)

* Actual LSST camera footprint (instead of statistical fill factor)

* Trailing losses

* “Fading”/statistical detection cutoff

* All SSOs have spectral types: S, C according to (Ivesić et al. 2001). Colors and filter transformations were taked from Vereš & Chesley (2017).

* False detections: DIA & CCD noise (Jones et al. 2017, Vereš & Chesley 2017)

## References

Grav, T., Jedicke, R., Denneau, L., Chesley, S., Holman, M. J., & Spahr, T. B. (2011). The Pan-STARRS synthetic Solar System model: A tool for testing and efficiency determination of the moving object processing system. Publications of the Astronomical Society of the Pacific, 123(902), 423.

Ivezić, Ž., Tabachnik, S., Rafikov, R., Lupton, R. H., Quinn, T., Hammergren, M., ... & Finlator, K. (2001). Solar system objects observed in the Sloan Digital Sky Survey commissioning data. The Astronomical Journal, 122(5), 2749.

Jones, R. L., Slater, C. T., Moeyens, J., Allen, L., Axelrod, T., Cook, K., ... & Petry, C. E. (2018). The large synoptic survey telescope as a near-earth object discovery machine. Icarus, 303, 181-202.

Vereš, P., & Chesley, S. R. (2017). High-fidelity simulations of the near-earth object search performance of the large synoptic survey telescope. The Astronomical Journal, 154(1), 12.


