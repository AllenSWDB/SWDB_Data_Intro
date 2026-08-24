# V1DD README

_README files serve as concise, human-readable description of the contents and structure of a folder and/or dataset. Most importantly, these files are meant to be a resource for YOU!_

_This file is written with Markdown formatting for readability; however, you are free to write in plain text._

## Overview

### Description
_Simple description of the dataset, what it contains, and what kinds of question it's useful for._

### Contacts
_Record key contacts, both at SWDB and beyond, who are knowledgable about the dataset._
- ...

### At a glance
_High level numbers or details about the dataset e.g. how many subjects and/or sessions were recorded? How many sessions per subject? Sometimes, this is actually easier to fill out at the end._
- ...

## Navigation
_Provide an overview on how the dataset is organized, such as how the folder directory is structured (we provided it this time!), file naming conventions, and how to navigate the many data files._

### Directory structure

```
data/
├── metadata/
│   └── V1DD_metadata.csv
├── <SUBJECT_ID>_V1DD_Filtered/                             # subject
│   ├── <SUBJECT_ID>_<ACQUISITION_DATE_TIME>_filtered_<FILTER_DATE_TIME>/
│   │   │                                                   # imaging volume
│   │   ├── <SUBJECT_ID>_<ACQUISITION_DATE_TIME>.nwb.zarr   # see subsection below
│   │   └── # various json files
└── # ... 3 other subjects
```

### Metadata
The metadata file, `data/metadata/V1DD_metadata.csv` provides curated session-level data for filtering. Remember that this file was created by querying the central database and pulls a filtered set of data files and columns. The current file contains the following relevant columns:
- <column_name>: <column description, if needed>
- ...

> Note: The `Filtered`/`filter` flag in the folder names indicate that the data has been filtered in some way. Specifically, this filtering refers to filtering the optical response to just the soma, and filters out non-soma responses.


### NWB file structure
_The NWB file is the data containing record. It has a lot of internal structure, which we would like to document as well._

```
<SUBJECT_ID>_<ACQUISITION_DATE_TIME>.nwb.zarr/
├── ...
│   ├── ...                    # comment
│   │   └── ...                # comment
│   └── ...                    # comment
├── ...
│   ├── ...                    # comment
│   ├── ...                    # comment
│   └── ...                    # comment
└── ...
```

## Dataset features

### Neurophysiological data (`processing/plane-{0..5}/`)
- _e.g. what recording modality was used? what are some relevant details about the modality?_
- _e.g. how many units or ROIs are available? what's the total population size?_
- _e.g. are the neural responses (QC'd)? if not, what processing or filtering needs to be do?_
- ...

#### Anatomy
- _e.g. what location / angle / layer?_
- ...

#### Cell types
- _e.g. what cell types were recorded? how were they accessed?_
- ...

### Behavioral data (`processing/behavior/`)
- _e.g. what types of behaviors were recorded?_
- _e.g. are the behavioral responses QC'd? if not, what processing or filtering needs to be done?_
- _e.g. was there any behavior training conducted prior to measurement? if so, what curricular details are important to keep in mind? what were the performance criteria for retention?_ ...

### Stimulus table (`intervals/stimulus_table/`)
- _e.g. what manipulations / experimental interventions were performed?_
- _e.g. what stimulus conditions were presented? what was the task structure?_
- _e.g. if multiple stimulus conditions, under what conditions or for what questions should each stimulus condition be analyzed?_
- ...

## Opportunities + Limitations
_Note down any opportunities that this dataset offers, in addition to limitations._

**Opportunities**
- ...

**Limitations**
- ...

## Misc
_Remember, this document is meant to be a tool for you! At any point, feel free to add sections and details as you see fit. The above format is very generic and may not be fully applicable to the dataset(s) that you're looking at. A non-exhaustic list of examples include:_
- _Code snippets about how to open the NWB file or access specific data quantities_
- _References, such as a [Markdown cheatsheet](https://www.markdownguide.org/cheat-sheet/)._