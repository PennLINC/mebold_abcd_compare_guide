<br>
<br>

### Abstract


### Project Lead
Taylor Salo

### Faculty Lead
Theodore D. Satterthwaite

### Analytic Replicator
Tien Tong

### Collaborators 
List to be collected

### Project Start Date
August 2023

### Current Project Status
Manuscript in preparation

### Datasets


### Github Repository
<https://github.com/PennLINC/mebold_abcd_compare_guide>
### Slack Channel:
#mebold-abcd-compare

### Cubic Project Directory Overview
`/cbica/projects/executive_function/mebold_trt/`

<br>
<br>

# CODE DOCUMENTATION  

All project analyses are described below along with the corresponding code on Github. The following outline describes the order of the analytic workflow:

*0.* Download data from FlyWheel and curate for OpenNeuro
*1.* Download from OpenNeuro
*2.* Run BABS



In each of the scripts, there is a variable `REPRO_DIR` or `repro_dir` that needs to be set to the directory where you're running the replication from.

<br>

### 0. Download data from FlyWheel

The steps to create the initial BIDS data can be found in `processing_code/curation`.
Briefly, the steps were to download the dicom tarballs from Flywheel and run heudiconv.
Because no-RF images are included in the dicoms, these were split into separate files.
The anatomical scans were refaced using AFNI.
Finally, the events files were converted to BIDS format.

The validated BIDS data were uploaded to OpenNeuro.
This is where the replication process can begin - 
with the datalad cloned BIDS data from OpenNeuro.

### 1. Download from OpenNeuro

As the `executivefunction` user on cubic we cloned the data from OpenNeudo using

```bash
micromamba activate babs
cd /cbica/projects/executive_function/mebold_trt/
datalad clone ///openneuro/ds005250
datalad get -J 10 .
```