# V1DD_README.md (instructor-version)

Readme files serve as concise, human-readable description of the contents and structure of a folder and/or dataset.

These files should be written in either plain text or lightly formatted with Markdown (which this file is using).

## Basic information
**Title**
V1 Deep Dive (V1DD)

**Description**
_Write a simple description of this dataset._

**Contacts.**
- Record which SWDB contacts are knowledgable about the dataset and about what aspects (if applicable)
- People / teams responsible for collecting the data

## Folder structure
_**(Part 2a)** Briefly describe how the folder is structured and any file naming conventions._

```
├── data/
│   ├── metadata/
│   │   └── V1DD_metadata.csv
│   ├── <SUBJECT_ID>_V1DD_Filtered/                             # subject
│   │   ├── <SUBJECT_ID>_<ACQUISITION_DATE_TIME>_filtered_<PREPROCESS_DATE_TIME>/
│   │   │   │                                                   # imaging volume
│   │   │   ├── <SUBJECT_ID>_<ACQUISITION_DATE_TIME>.nwb.zarr   # see subsection below
│   │   │   └── # various json files
└── └── # Other subjects
```

## Data structure
_**(Part 2b)** Instructions: Provide a brief description of how the folder is structured and any file naming conventions._

### Metadata
The metadata file (`data/metadata/V1DD_metadata.csv`) enables querying and filtering datasets by experimental attributes and retrieving the corresponding data files.

Relevant columns / attributes:
- `subject_id` (int): Unique subject id (n=4) [numeric]
- `golden_mouse` (bool): True if mouse with EM construction; only 1 mouse (42986) with EM [bool]
- `genotype` (str): Genotype line for ophys
- `modality` (list[str]): Collected data modalities, e.g. ['planar optical physiolgoy', 'behavior videos'] [list of strings]
- `column` (str): Imaging column
- `volume` (str): Imaging volume

**[QUESTION] Should we introduce how data was collect and the "column" and "volume" info from data book here?**


### NWB File Structure
_**(Part 2c)** Instructions: Document the minimal code to open a data file -- you'd be surpised how easy it to forget!_

```python
import pynwb
from hdmf_zarr import NWBZarrIO

nwbfile_path = <PATH_TO_NWB_ZARR_HERE>
io = NWBZarrIO(nwbfile_path_zarr, "r")  # [QUESTION] is this still neded?
nwbfile_read = io.read()

```

_**(Part 2d)** Instructions: Provide a bried description of how each file is structured._
```
├── root/
│   ├── stimulus/  # stimulus sets
│   │   └── V1DD_metadata.csv
│   ├── processing/                             # main data of interest!!
│   │   ├── behavior/                           # - Processed behavioral data
│   │   │   ├── running_speed/                  #   - TimeSeries
│   │   │   │   ├── data                        #     - (n_timestamps,)
│   │   │   │   └── timestamps                  #     - (n_timestamps,). units: seconds
│   │   │   └── eye_tracking/                   #   - DynamicTable
│   │   │   │   └── table                       #     - (n_timestamps, n_columns)
│   │   ├── plane-{0-5}/                        # - Single plane ophys data
│   │   │   ├── dff/                            #   - (n_timestamps, n_rois). units: seconds
│   │   │   ├── image_segmentation/             #   - (n_timestamps, n_rois)
│   │   │   └── # QUESTION: ANY OTHER RELEVANT FIELDS
│   ├── epochs/                                 # start and top times for all stimulus epochs
│   │   │   └── table                           # - {stim_name, start_time, stop_time, duration}


```


## Details
_[Part 3] Instructions: Include additional details and observations here, particularly those that are not apprent or present in the metadata or data itself.

### Neural activity

#### Optical physiology
- ROIS

### Behavior
- ...

### Epoch and stimulus tables
- Full field drifting gratings
- Windowed drifting gratins
- Locally sparse noise 

**[TODO] Pull from [databook](https://allenswdb.github.io/physiology/ophys/V1DD/V1DD-stimuli.html)**



## References

### V1DD description
- [SWDB databook](https://allenswdb.github.io/physiology/ophys/V1DD/V1DD-overview.html)
- [Original V1DD description](https://github.com/zhuangjun1981/v1dd_physiology/blob/main/v1dd_physiology/meta/database_description.md) (internal access only)

### README files
- [Harvard Medical School, Research Data Management Working Group. "README Files." Data Management.](https://datamanagement.hms.harvard.edu/collect-analyze/documentation-metadata/readme-files)
- [Datascience Readme template.](https://github.com/pragyy/datascience-readme-template)

### Markdown
- [Markdown guide](https://www.markdownguide.org/)
- Quick and handy [cheatsheet](https://www.markdownguide.org/cheat-sheet/).

## FAQs

**We're provided with Databook, which contains all of this information. Why do I need to recreate my own README file?**
- Importance of self-documenting / everything
- There is no databook in the real world