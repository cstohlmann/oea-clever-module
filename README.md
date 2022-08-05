# Clever (Participation Reports) Module
Clever offers single sign-on access for students and teachers to their digital learning applications. This Clever module, developed by Fresno Unified School District, provides application usage data for all the applications used by an education system that sign on through Clever. The data is retrieved through the [Participation Reports](https://support.clever.com/hc/s/articles/360049642311) feature available from Clever. 

This data will allow education leaders to see which applications are being used for learning. It will contribute to the Digital Learning Insights use case, by allowing the OEA community to combine it with learning outcome data.  

## Module Setup
1. Import the Clever_main_pipeline template into your Synapse workspace.
2. Import the [Clever module class notebook]() into your Synapse workspace. After ensuring your Synapse workspace contains both the Clever module notebooks (Clever_py and Clever_module_ingestion), trigger the main pipeline. Two databases will be created upon the successful trigger: s2_clever and sqls2_clever.
3. Download the Power BI template file Clever Module Dashboard and connect to your Synapse workspace serverless SQL endpoint. You will want to change the dashboard template from Import to a directQuery from the sqls2_clever database.

## Problem Statement
Collecting data related to the digital activity/engagement is crucial to understanding the success and struggle of students. As digital learning continues to become more prevalent, understanding the resources that students use is fundamental to better supporting student success, in and out of the classroom.  

## Module Impact
This Clever Participation Reports module for OEA will leverage the Azure Synapse environment to aid education systems in bringing this data to their own Azure data lake for analysis. This includes a pipeline for extracting the digital activity/engagement from an education institution, providing a more holistic representation of online teaching and learning activities. The PowerBI templates included in this module can be used by system and school leaders to show:

- Which resources/applications are being used across the education system over time
     * Number of different resources used by users over a given day
     * Specific applications being used by any user, and the number of times that resource was used
     * Average number of applications a student uses, per grade or per school

These dashboard examples represent only data from the Participation Reports from Clever. There are many other Clever reports that could be used instead, or in combination with these Participation Reports. When this data is combined with other data sources, they can illustrate how patterns of digital activity relate to learning outcomes, or answering questions related to the equity of access. With such combined data, education systems can start to analyze interventions help to improve student learning with digital tools.  

## Data Sources
The module will connect to Clever's SFTP server and pull CSV files from daily-participation and resource-usage. The Clever pipeline will only bring over new CSV files.

## Module Components 
Out-of-the box assets for this OEA module include: 
1. [Sample Datasets](): Ingest sample data to understand the utility and functionality of the pipelines and notebooks.
2. [Pipeline](): 3 pipeline templates - One main pipeline for data extraction and ingestion to stage 2, one sub-pipeline which lands Clever data to the Synapse workspace data lake, and another sub-pipeline that extracts the test data provided within this module to the Synapse workspace.
3. [Notebook](): 2 notebooks - A class notebook that defines the functions of data ingestion/processing the data from stage 1 to stage 2 within Synapse (Clever_py), and an ingestion notebook used to process the data by calling the functions in the class notebook (Clever_module_ingestion).
4. [PowerBI template](): A Power BI sample template making it easy to interact with Clever data. See below for examples of developed PowerBI dashboard pages.

Explanation  | Usage Summary
:-------------------------:|:-------------------------:
![](https://github.com/cstohlmann/oea-clever-module/blob/main/docs/images/Clever%20Module%20Explanation%20Page.png)  |  ![](https://github.com/cstohlmann/oea-clever-module/blob/main/docs/images/Clever%20Module%20Dashboard%20Sample.png) 
 

The Clever module [welcomes contributions.](https://github.com/microsoft/OpenEduAnalytics/blob/main/CONTRIBUTING.md) 

This module was developed by Kwantum Analytics in partnership with Fresno Unified School District. The architecture and reference implementation for all modules is built on [Azure Synapse Analytics](https://azure.microsoft.com/en-us/services/synapse-analytics/) - with [Azure Data Lake Storage](https://docs.microsoft.com/en-us/azure/storage/blobs/data-lake-storage-introduction) as the storage backbone,  and [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/) providing the role-based access control.

### Additional Information
| Resource | Description |
| --- | --- |
| [Overview of Clever API](https://dev.clever.com/docs/api-overview) | Intro to Clever API, what it can do, and how it can be used. |
| [Clever API v3.0 Data Schema](https://docs.google.com/spreadsheets/u/1/d/e/2PACX-1vTY8WSC--TBok-cHjG8itGyqnrj7sCkfyWVzIxeLybwzryW01L9qD8xwhoJDBlWrjOkciOXV34G9ejH/pubhtml) | Landing page of documentation on the v3.0 Clever data schema. |

# Legal Notices

Microsoft and any contributors grant you a license to the Microsoft documentation and other content
in this repository under the [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
see the [LICENSE](LICENSE) file, and grant you a license to any code in the repository under the [MIT License](https://opensource.org/licenses/MIT), see the
[LICENSE-CODE](LICENSE-CODE) file.

Microsoft, Windows, Microsoft Azure and/or other Microsoft products and services referenced in the documentation
may be either trademarks or registered trademarks of Microsoft in the United States and/or other countries.
The licenses for this project do not grant you rights to use any Microsoft names, logos, or trademarks.
Microsoft's general trademark guidelines can be found at http://go.microsoft.com/fwlink/?LinkID=254653.

Privacy information can be found at https://privacy.microsoft.com/en-us/

Microsoft and any contributors reserve all other rights, whether under their respective copyrights, patents,
or trademarks, whether by implication, estoppel or otherwise.
