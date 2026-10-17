# Data acquisition and interpretation

## Approved source
Use only the [UCI Bike Sharing dataset](https://archive.ics.uci.edu/dataset/275/bike+sharing+dataset) for core historical metrics.
[Direct ZIP download](https://archive.ics.uci.edu/static/public/275/bike%2Bsharing%2Bdataset.zip).
DOI: https://doi.org/10.24432/C5W894.
Citation: Fanaee-T, H. (2013). Bike Sharing [Dataset]. UCI Machine Learning Repository.
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/): preserve attribution, link the licence and disclose modifications in reports and redistributed derived examples.

The source describes hourly/daily Capital Bikeshare rentals during 2011–2012 and accompanying weather/calendar variables. Archive contains hour.csv, day.csv and Readme.txt. UCI lists 17,389 instances and a 273.4 KB archive; treat these as catalogue metadata, not a checksum or guaranteed parsed row count.

## Reproducible acquisition
1. Download the ZIP from the exact official URL; no account or paid API required.
2. Preserve the ZIP under data/raw/uci-bike-sharing/. Extract only expected filenames inside that directory.
3. Compute SHA-256 of the archive and each extracted file. Record retrieval UTC time, URL, byte size, parsed row counts, columns and min/max dates in data/metadata/source_manifest.json.
4. Preserve Readme.txt under data/reference/ along with source/licence references and any dictionary discrepancies.
5. Validate schema, data types, date/hour keys, category codes, count identity, missing cells, missing grid slots and bounds. Save a validation report.
6. Reconcile hourly/daily rental counts; freeze input hashes before metric development.
7. Create labelled derived fixtures separately. Never edit raw files.

Use a repeatable downloader in the team implementation plus a manual download fallback. Record failures, redirects and source changes; a changed hash requires review. Offline operation must work after initial data/model downloads.

## Dictionary essentials
- instant: row identifier; dteday: date; hr: hour in hourly file only.
- yr: 0=2011, 1=2012; mnth: 1–12; holiday: source holiday flag; workingday: neither weekend nor holiday.
- weekday: preserve and verify mapping against dates and archive documentation before assigning labels.
- season: 1 winter, 2 spring, 3 summer, 4 fall per UCI; use source categories rather than inferring calendar seasons.
- weathersit: 1 clear/few/partly cloudy, 2 mist/cloudy, 3 light snow/rain conditions, 4 severe rain/snow/fog conditions. Preserve full original definitions in the dictionary.
- temp, atemp, hum, windspeed are normalised values. Do not label raw values as physical units. UCI documents hourly temp conversion using −8 to 39 Celsius, and atemp using −16 to 50 Celsius. Any conversion must cite its applicable scale; keep normalised values for core reporting.
- casual, registered: rental counts by user category; cnt: combined rental count.

## Limitations
No station inventory, availability, individual rider identities, revenue or unmet demand. Absent hourly records are not confirmed zero rentals. Source-local time is not a documented UTC series. Daily/hourly grains must stay separate. Weather and seasonal associations are descriptive and confounded; sparse groups require abstention. Historical findings must not be described as current operations.

See [source register](SOURCE_REGISTER.md), [metadata contract](metadata/README.md) and [KPI policy](../project/KPI_SPECIFICATION.md).
