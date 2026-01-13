# Geoscience Australia RTC

This repository is a fork of the NASA JPL RTC project detailed below. Changes have been made for creating Geoscience Australia production data. The main changes include:
-  Updating the isce3 project from 0.15.0 to 0.24.4 to include bug fixes for applying atmospheric corrections identified by GA.
-  Updates to project metadata to reference Geoscience Australia processing settings and contact details

This main project RTC should be monitored for updates that can be merged into this repository. For example, if the NASA JPL OPERA team decide to also bump the isce3 version on their main branch.


# RTC
NASA's Observational Products for End-Users from Remote Sensing Analysis (OPERA) Radiometric Terrain-Corrected (RTC) SAR backscatter from Sentinel-1 (RTC-S1) Science Application Software developed by the OPERA Algorithm Development Team at NASA's Jet Propulsion Laboratory (JPL).

### Versioning

To update/bump the version number, both the [Dockerfile](./Docker/Dockerfile) and [version.py](./src/rtc/version.py) files must be updated.

### Install

Instructions to install RTC under a conda environment.

1. Download the source code:

```bash
git clone https://github.com/opera-adt/RTC.git RTC
```

2. Install `isce3`:

```bash
conda install -c conda-forge isce3
```

3. Install `s1-reader` via pip:
```bash
git clone https://github.com/opera-adt/s1-reader.git s1-reader
conda install -c conda-forge --file s1-reader/requirements.txt
python -m pip install ./s1-reader
```

4. Install `RTC` via pip:
```bash
git clone https://github.com/opera-adt/RTC.git RTC
python -m pip install ./RTC
```



### Usage

The command below generates the RTC product:

```bash
rtc_s1.py <path to rtc yaml file>
```

To compare the RTC-S1 products, use `rtc_compare.py`.

```bash
python rtc_s1.py <1st product HDF5> <2nd product HDF5>
```

# License

This project is licensed under the Apache License, Version 2.0.

Copyright © 2021 California Institute of Technology (“Caltech”). U.S. Government sponsorship acknowledged.

All rights reserved.

Modifications © 2025 Geoscience Australia.

See the LICENSE and NOTICE files for full license text and attribution.