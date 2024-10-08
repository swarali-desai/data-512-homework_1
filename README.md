# Wikipedia Article Traffic Analysis (2015-2024)

[DATA-512 | Homework 1 | Professionalism & Reproducibility](https://docs.google.com/document/d/1ovpmb9BXWrDVP1a-AKrT0E36XZC7N4n8-0iUfgQzKVg/edit)

# Goal

This project aims to construct, analyze, and publish a dataset of monthly article traffic for a select set of pages from English Wikipedia from July 1, 2015 through September 30, 2024. The dataset will provide insights into page view trends over time, allowing for analysis of article popularity and traffic patterns from desktop and mobile devices.

The motivation for project is to gain hands-on experience in adhering to best practices for open scientific research, ensuring reproducibility by providing accessible data, maintaining transparent documentation, and complying with licensing standards.

# License

## Source Data

The source data for this project comes from the Wikimedia Foundation using their publicly exposed [Pageviews API](https://doc.wikimedia.org/generated-data-platform/aqs/analytics-api/reference/page-views.html).

[Wikimedia Foundation Terms of Use](https://foundation.wikimedia.org/wiki/Policy:Terms_of_Use) allows free use of content while requiring attribution, preserving open licenses, and respecting copyright and user rights. To ensure that this project complies with Wikimedia's Terms of Use, I've provided the required attribution referencing the original source of data.

Summary of ToU:
The Terms of Use (ToU) for Wikimedia apply to the dataset I've created because it likely uses data sourced from Wikimedia projects, such as Wikipedia. According to the ToU, any reuse or modification of content must comply with Creative Commons Attribution-ShareAlike License (CC BY-SA). This means that the dataset can be shared and adapted, provided that proper attribution is given to the original sources, and any derivative works are shared under the same license. Additionally, adherence to legal policies, privacy protection, and responsible use of the data is required.

## Data aquisition code

Snippets of the below code were taken from a code example developed by Dr. David W. McDonald for use in DATA 512, a course in the UW MS Data Science degree program. This code is provided under the Creative [Commons CC-BY license](https://creativecommons.org/licenses/by/4.0/). Revision 1.3 - August 16, 2024

This repository uses a subset of the English Wikipedia that represents a large number of articles related to rare diseases. This list of pages was collected by using a database of rare diseases maintained by the [National Organization for Rare Diseases (NORD)](https://rarediseases.org) and matching them to Wikipedia articles that are either about a rare disease or have a section that mentions a rare disease.

# API Documentation

[Pageviews API](https://doc.wikimedia.org/generated-data-platform/aqs/analytics-api/reference/page-views.html): Page view analytics provides data about page views for Wikimedia projects starting July 2015.

[Pandas](https://pandas.pydata.org/docs/reference/index.html): Python data processing library

[Matplotlib](https://matplotlib.org/stable/api/index.html): Library used to create graphs

# Usage

Entire code for reproducing the results are present in the [monthly_article_views_data_analysis.ipynb](data-512-homework_1 /monthly_article_views_data_analysis.ipynb) file.
We just have to run the cells in order to produce the same results.

You can use jupyter to run this file locally or even google colab (needs access to google colab). One can use the `Run All Cells` or `Restart Kernel` and `Run All Cells` option of the jupyter notebook.

Note: The data aquisition step may require different time to run which can range from 10-30 minutes based on the system used and network.

# Result files

Running the [monthly_article_views_data_analysis.ipynb](data-512-homework_1 /monthly_article_views_data_analysis.ipynb) file produces dataset for desktop, mobile and cummulative views for the monthly article traffic for a select set of pages from English Wikipedia from July 1, 2015 through September 30, 2024. These datasets are stored in a JSON format under the [article_views_json_files](data-512-homework_1 /article_views_json_files) folder.

Structure of each JSON dataset is as follows:

```
{
    string: [                         #Page title
        {
            "project": string,        #Wikimedia domain and subdomain
            "article": string,        #Page title
            "granularity": string,    #Time interval between datapoints
            "timestamp": string,      #Timestamp in YYYYMMDDHH format
            "agent": string,          #Type of user agent
            "views": integer          #Number of page views
        }
  ]
}
```

The [monthly_article_views_data_analysis.ipynb](data-512-homework_1 /monthly_article_views_data_analysis.ipynb) also generated plots which are analysed. These plots are visualized using the pandas and matplotlib libraries and can be viewed within the notebook but they are also saved as a .png in the [article_views_stats_plots](data-512-homework_1 /article_views_stats_plots) folder.

### Important Notes for Users

-   **Data Inconsistencies**: Some articles may have missing data for certain months due to limitations in the API or data availability issues.
-   **API Changes**: Future updates to the Wikimedia API may impact the consistency of data over the entire analysis period.
-   **Article Renaming**: If an article was renamed during the analysis period, it might appear as two separate entries.

Please keep these factors in mind when utilizing this project for research or analysis purposes.

This repository is open for collaboration and further research using proper guidelines of the license.
