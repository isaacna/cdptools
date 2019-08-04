# cdptools

[![build status](https://travis-ci.com/CouncilDataProject/cdptools.svg?branch=master)](https://travis-ci.com/CouncilDataProject/cdptools)
[![codecov](https://codecov.io/gh/CouncilDataProject/cdptools/branch/master/graph/badge.svg)](https://codecov.io/gh/CouncilDataProject/cdptools)


Making City Council data more accessible and actions taken by city council members more discoverable and trackable.

## Features
* From video -> storing audio -> generating and storing transcripts -> indexing -> analysis.
* Modular system for gathering city council events, transcribing, and indexing them to make searchable.
* Data pipelines are highly customizable to fit your cities needs.
* Database schema allows for simple querying of event, body, member, or voting history of a city council.


## Quickstart Documentation

**For Seattle:**
```python
from cdptools.databases import CloudFirestoreDatabase

db = CloudFirestoreDatabase("cdp-seattle")
matching_events = db.search_events("bicycle infrastructure, pedestrian mobility, greenways")
# Returns list of EventMatch objects
# [EventMatch, EventMatch, ...]

all_events = db.select_rows_as_list("event")
# Returns list of dictionaries with event information
# [{"event_id": "0123", ...}, ...]
```

## Installation
`cdptools` is available on [pypi.org](https://pypi.org/project/cdptools/).

#### Per city installation:
* Seattle: `pip install cdptools[google-cloud]`

#### All city installation:
`pip install cdptools[all]`

Please view the [examples](/examples) directory which contains Jupyter notebooks with more examples on how to use CDP
databases and file stores.

For additional information on system design, look at [system_design.md](docs/system_design.md).

**Free software: BSD-3-Clause license**

This package was created with [Cookiecutter](https://github.com/audreyr/cookiecutter).
