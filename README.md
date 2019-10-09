# United Kingdom Local Authority District name/code changes

Tracking changes to Local Authority District administrative boundaries, names and codes, from
2011 to 2018.

The data processing is open source, with the usual lack of warranty of any kind - do raise an
[issue](https://github.com/tomalrussell/uklad-changes/issues) or offer a fix if you find a
problem.

## Data

The output data is a single table, where column names include either `nm` (name) or `cd` (code)
and a two-digit year. For example, `lad11nm` is the LAD name in 2011.

There are several kinds of change, as in the extract below:
- Hartlepool has the same name and code from 2011-2018
- Cornwall and the Isles of Scilly are merged for census reporting purposes (the
  `_census_merged` columns)
- Shepway changes name to Folkestone and Hythe in 2018
- Armagh, Banbridge and Craigavon join to become "Armagh City, Banbridge and Craigavon" in 2015

lad11nm | lad11cd | lad11nm_census_merged | lad11cd_census_merged | lad16nm | lad16cd | lad17nm | lad17cd | lad18nm | lad18cd
------- | ------- | --------------------- | --------------------- | ------- | ------- | ------- | ------- | ------- | -------
Hartlepool | E06000001 | Hartlepool | E06000001 | Hartlepool | E06000001 | Hartlepool | E06000001 | Hartlepool | E06000001
Cornwall | E06000052 | Cornwall, Isles of Scilly | E41000052 | Cornwall | E06000052 | Cornwall | E06000052 | Cornwall | E06000052
Isles of Scilly | E06000053 | Cornwall, Isles of Scilly | E41000052 | Isles of Scilly | E06000053 | Isles of Scilly | E06000053 | Isles of Scilly | E06000053
Shepway | E07000112 | Shepway | E07000112 | Shepway | E07000112 | Shepway | E07000112 | Folkestone and Hythe | E07000112
East Hertfordshire | E07000097 | East Hertfordshire | E07000097 | East Hertfordshire | E07000242 | East Hertfordshire | E07000242 | East Hertfordshire | E07000242
Armagh | 95CC | Armagh | 95CC | Armagh City, Banbridge and Craigavon | N09000002 | Armagh City, Banbridge and Craigavon | N09000002 | Armagh City, Banbridge and Craigavon | N09000002
Banbridge | 95FF | Banbridge | 95FF | Armagh City, Banbridge and Craigavon | N09000002 | Armagh City, Banbridge and Craigavon | N09000002 | Armagh City, Banbridge and Craigavon | N09000002
Craigavon | 95LL | Craigavon | 95LL | Armagh City, Banbridge and Craigavon | N09000002 | Armagh City, Banbridge and Craigavon | N09000002 | Armagh City, Banbridge and Craigavon | N09000002


## Sources

All data is derived from open government data, supplied under the [Open Government
License](http://www.nationalarchives.gov.uk/doc/open-government-licence/version/3/). More
details on the [ONS Geography licenses](https://www.ons.gov.uk/methodology/geography/licences)

Access via:
- [Office for National Statistics Open Geography Portal](https://geoportal.statistics.gov.uk/)
- [UK Data Service Census Support (InFuse)](http://infuse.ukdataservice.ac.uk/help/definitions/2011geographies/index.html)

Copyright statements:
- Contains National Statistics data © Crown copyright and database right 2019
- Contains OS data © Crown copyright and database right 2019
- Contains NRS data © Crown copyright and database right 2019 Source: NISRA : Website: www.nisra.gov.uk

Local Authority Districts (December 2011) GB BFC (Britain, Full, Clipped)
- https://opendata.arcgis.com/datasets/8c398b60a71d44e2bdf8b5b3bb951988_0.zip?outSR=%7B%22wkid%22%3A27700%2C%22latestWkid%22%3A27700%7D

Local Authority Districts (December 2015) Full Clipped Boundaries in Great Britain
- https://opendata.arcgis.com/datasets/8edafbe3276d4b56aec60991cbddda50_0.zip?outSR=%7B%22wkid%22%3A27700%2C%22latestWkid%22%3A27700%7D

Local Authority Districts (December 2016) Full Clipped Boundaries in the UK
- https://opendata.arcgis.com/datasets/7ff28788e1e640de8150fb8f35703f6e_0.zip?outSR=%7B%22latestWkid%22%3A27700%2C%22wkid%22%3A27700%7D

Local Authority Districts (December 2017) Full Clipped Boundaries in the UK
- https://opendata.arcgis.com/datasets/fab4feab211c4899b602ecfbfbc420a3_0.zip?outSR=%7B%22latestWkid%22%3A4326%2C%22wkid%22%3A4326%7D

Local Authority Districts (December 2018) Full Clipped Boundaries UK
- https://opendata.arcgis.com/datasets/b2d5f4f8e9eb469bb22af910bdc1de22_0.zip?outSR=%7B%22wkid%22%3A27700%2C%22latestWkid%22%3A27700%7D

Local Authorities area list (UK, Census Merged, 2011)
- Reference: http://infuse.ukdataservice.ac.uk/help/definitions/2011geographies/index.html
- List: http://infuse.ukdataservice.ac.uk/help/definitions/2011geographies/local-authority-area-list2011.csv
- Boundaries: https://borders.ukdataservice.ac.uk/ukborders/easy_download/prebuilt/shape/infuse_dist_lyr_2011_clipped.zip


Note that Northern Ireland has the largest post-2011 change, with 11 local government districts
since 1 April 2015; previously 26 councils since 1973.


## Note on notebooks

When working with jupyter notebooks in git, consider using
[nbstripout](https://github.com/kynan/nbstripout) to automatically remove data and cell outputs
before committing.

Install:

	pip install --upgrade nbstripout
	cd /path/to/repository
	nbstripout --install
