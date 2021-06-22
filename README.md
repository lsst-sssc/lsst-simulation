# LSST Simulation Issues
Repository to collect feedback/issues for the simulates SolSys Products DB.


# Release notes SSPDB, June 2021

The Solar System Products Data Base (SSPDB) contains a full density simulation of Solar System Object observations for the full 10 years of the Vera C. Rubin Observatory's Legacy Survey of Space and Time (LSST).
The aim of the SSPDB is to give the Solar System Science Collaboration (SSSC) a preview of what LSST data catalogs will look like. 
This second relase of the SSPDB is intended to serve as a testing ground during the LSST SSSC sprint 2021. Future updates of the SSSPDB will add fidelity and include additional data in order to provide as complete a mock catalog of LSST Solar System observations as possible.

## DB Realization
The SSPDB is currently realized as a MySQL database with three tables:

* DIASource
* SSSource
* SSObject
* MPCORB

The DIASource table contains information on individual observations of Solar System Objects (SSOs).
The SSObject table contains physical characteristics (slopes and magnitudes) computed based on LSST observations.
The MPCORB table contains orbit data for the SSO input populations.
This release does not include the noise table in the database, but noise can be obtained from files.
 
Table schemata have been implemented according to the following templates:
https://docs.google.com/spreadsheets/d/1E0rTlvuJC0CvpLNsuWLK0x70uhpZww4v6GB5QkiQr-Q

As of this moment several columns in the SSPDB are empty or NULL. Those will be filled over the course of the upcoming SSPDB updates.

## Accessing the SSPDB
The SSPDB can be accessed via the SSSC Jupyter Hub @ https://sssc.dirac.institute

The Postgres database is located @ pg.dirac.institute (accessible from within JupyterHub only)

## SSO Input Populations 
Synthetic Solar System Model (S3M, Grav et al. 2011) 


## Survey Simulation
Operations Simulation (OpSim) run Feature Based Scheduler version 1.7 (baseline_nexp2_v1.7.1_10yrs) @ 
http://astro-lsst-01.astro.washington.edu:8081/

## Observation Simulator
Naidu et al. (JPL) @
https://github.com/AsteroidSurveySimulator/objectsInField

### Settings/features

* N-body orbit propagation (perturbers: planets + Pluto/Charon)

* Actual LSST camera footprint (instead of statistical fill factor)

* Trailing losses

* Magnitude errors

* (H, G) magnitude fits (note: it's _not_ H, G12, despite the column names)

* Astrometric errors

* All SSOs have spectral types: S, C according to (Ivezić et al. 2001). Colors and filter transformations were taked from Vereš & Chesley (2017).

* False detections: DIA & CCD noise (Jones et al. 2017, Vereš & Chesley 2017) (available only as files)

## References

Grav, T., Jedicke, R., Denneau, L., Chesley, S., Holman, M. J., & Spahr, T. B. (2011). The Pan-STARRS synthetic Solar System model: A tool for testing and efficiency determination of the moving object processing system. Publications of the Astronomical Society of the Pacific, 123(902), 423.

Ivezić, Ž., Tabachnik, S., Rafikov, R., Lupton, R. H., Quinn, T., Hammergren, M., ... & Finlator, K. (2001). Solar system objects observed in the Sloan Digital Sky Survey commissioning data. The Astronomical Journal, 122(5), 2749.

Jones, R. L., Slater, C. T., Moeyens, J., Allen, L., Axelrod, T., Cook, K., ... & Petry, C. E. (2018). The large synoptic survey telescope as a near-earth object discovery machine. Icarus, 303, 181-202.

Vereš, P., & Chesley, S. R. (2017). High-fidelity simulations of the near-earth object search performance of the large synoptic survey telescope. The Astronomical Journal, 154(1), 12.


