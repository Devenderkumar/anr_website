+++
description = "Excerpts of electronic Form 990 and 990-EZ filings, converted to spreadsheet form. Additional fields being added regularly."
title = "IRS 990 Filings -- Spreadsheet Excerpts"

+++

This repository consists of spreadsheet extracts from the annual tax returns of U.S. tax-exempt organizations filed with the IRS for tax years 2010 to 2017. This work is derived from the official IRS Form 990 e-file public dataset. It reflects a sustained effort to organize and simplify the original data. (Additional cleaning and analysis are performed to create the data seen on [Open990](https://www.open990.com). Target users include journalists, researchers, nonprofit organizations, and funders of nonprofit organizations.

In addition to flattening data from the Forms 990 and 990-EZ into spreadsheets, we have standardized field names over time by paper location. This simplifies the task of finding and retrieving information of interest.

Although we have made every effort to reproduce these data faithfully, these files are the result of a curation process with no guidance from the IRS. They are provided AS IS AND WITH ABSOLUTELY NO WARRANTY, EXPRESS OR IMPLIED. For more information about challenges and solutions when working with the original data, please see [this review](/posts/2018/06/the-irs-990-e-file-dataset-getting-to-the-chocolatey-center-of-data-deliciousness/) written by the dataset authors.

## Data currently available

This dataset is a work in progress, and we are adding additional fields and forms as we are able to validate them. We currently offer the following documents:

- `irs990_main`: Select "flat" (non-list) fields from the Form 990, including the Header, Part I (Summary), Part VI-A (Governing Body), Part VI-B (Policies), and Part X (Balance Sheet).
    - **Download: [2017](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_main/2017.csv), [2016](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_main/2016.csv), [2015](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_main/2015.csv), [2014](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_main/2014.csv), [2013](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_main/2013.csv), [2012](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_main/2012.csv), [2011](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_main/2011.csv), [2010](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_main/2010.csv)**
- `irs990_part_07b_list`: Form 990 Part VII, Section B, list of highly compensated independent contractors. 
    - **Download: [2017](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_part_07b_list/2017.csv), [2016](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_part_07b_list/2016.csv), [2015](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_part_07b_list/2015.csv), [2014](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_part_07b_list/2014.csv), [2013](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_part_07b_list/2013.csv), [2012](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_part_07b_list/2012.csv), [2011](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_part_07b_list/2011.csv), [2010](https://irs-990-spreadsheets.s3.amazonaws.com/irs990_part_07b_list/2010.csv)**
- `irs990ez_part_03_list`: Form 990-EZ Part III, list of program service accomplishments.
    - **Download: [2017](https://irs-990-spreadsheets.s3.amazonaws.com/irs990ez_part_03_list/2017.csv), [2016](https://irs-990-spreadsheets.s3.amazonaws.com/irs990ez_part_03_list/2016.csv), [2015](https://irs-990-spreadsheets.s3.amazonaws.com/irs990ez_part_03_list/2015.csv), [2014](https://irs-990-spreadsheets.s3.amazonaws.com/irs990ez_part_03_list/2014.csv), [2013](https://irs-990-spreadsheets.s3.amazonaws.com/irs990ez_part_03_list/2013.csv), [2012](https://irs-990-spreadsheets.s3.amazonaws.com/irs990ez_part_03_list/2012.csv), [2011](https://irs-990-spreadsheets.s3.amazonaws.com/irs990ez_part_03_list/2011.csv), [2010](https://irs-990-spreadsheets.s3.amazonaws.com/irs990ez_part_03_list/2010.csv)**

See [data dictionary (PDF)](/downloads/irs-990-spreadsheets/data-dictionary-2019-04-07.pdf) for details.

## How the data are organized

IRS 990 data are inherently hierarchical. Data from two primary forms will be captured in this repository: the 990 (“Return of Organization Exempt from Income Tax”) and 990-EZ (“Short Form”). Each form consists of many parts and sections, some of which contain lists. In addition, the repository will include data from several schedules, which collect additional information from a subset of organizations. 

Our dataset is designed to flatten this hierarchy as much as possible without losing information. We do this by supplying each list in a separate spreadsheet, which we link to each other, to a "main" spreadsheet, and to applicable schedules via a unique numeric filing ID supplied by the IRS. 

Within each spreadsheet, the column names reflect a line number corresponding to its location on the paper form whenever possible. In some cases, the underlying e-filed data contain several fields that the paper form represents with a single text box. In these cases, we provide additional contextual identifying information. In cases where variables have changed location across years, this change is indicated within the column name or other documentation. 

## Accessing the 990 spreadsheets on AWS

Data files are organized as follows:

```
s3://irs-990-spreadsheets/<form-or-table-name>/<year>.csv
```

which is equivalent to

```
https://irs-990-spreadsheets.s3.amazonaws.com/<form-or-table-name>/<year>.csv
```

where

<year> is defined as the end of the tax period identified on the filing. 
	
The dataset is designed to facilitate either offline data exploration or direct querying via Amazon Athena. An Athena tutorial is forthcoming. 

## License

Attribution 4.0 International [(CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)

## Additional documentation

* [Data dictionary](/downloads/irs-990-spreadsheets/data-dictionary-2019-04-07.pdf) for variables and their data types
* [Changes in forms over time](/downloads/irs-990-spreadsheets/form-990-variations-2009-2018.xlsx) traces changes to the wording/numbering of the Form 990, 2009 -- 2018

### And from the IRS:

* [Form 990 2018](https://www.irs.gov/pub/irs-prior/f990--2018.pdf)
* [Form 990 2018 Instructions](https://www.irs.gov/pub/irs-prior/i990--2018.pdf)
* [Form 990-EZ 2018](https://www.irs.gov/pub/irs-prior/f990ez--2018.pdf)
* [Form 990-EZ 2018 Instructions](https://www.irs.gov/pub/irs-prior/i990ez--2018.pdf)

## Contact for updates

If you would like to be notified when we post new data to this AWS repository, please use the contact form below with the subject line "Data update request." If you have any questions, concerns, or suggestions about the dataset, please use the form below or email us at [info@appliednonprofitresearch.com](info@appliednonprofitresearch.com).

## About the authors

[Applied Nonprofit Research, LLC](https://www.appliednonprofitresearch.com) was formed by data engineer [David Bruce Borenstein](https://www.appliednonprofitresearch.com/contact) and social science researcher [Heather Kugelmass](https://www.appliednonprofitresearch.com/contact). Its mission is to facilitate the use of public information surrounding the U.S. nonprofit sector. In addition to maintaining this dataset, Applied Nonprofit Research provides data and infrastructure for [Open990](https://www.open990.com/) -- a free directory of private foundations, charities, and other nonprofits -- and offers consulting services.
