---
title: File details- shipment_method_store.csv
last_updated: Sep 14, 2020
template: data-import-template
originalLink: https://documentation.spryker.com/v5/docs/file-details-shipment-method-storecsv
originalArticleId: e8ad47a1-4e94-4211-9564-dda73b7b0e4c
redirect_from:
  - /v5/docs/file-details-shipment-method-storecsv
  - /v5/docs/en/file-details-shipment-method-storecsv
---

This article contains information about the [Shipment Method](/docs/scos/user/features/{{page.version}}/shipment-feature-overview.html) and Store relation to be added to your Spryker Demo Shop.

The *shipment_method_store.csv* file contains the links between each shipment method used by each existing store.

## Import file parameters
These are the header fields to be included in the .csv file:

| Field Name | Mandatory | Type | Other Requirements/Comments | Description |
| --- | --- | --- | --- | --- |
| **shipment_method_key** | Yes | String | Can be imported from the content that was loaded using the [shipment.csv](/docs/scos/dev/data-import/{{page.version}}/data-import-categories/commerce-setup/file-details-shipment.csv.html) file.| Identifier of the shipment method. |
| **store** | Yes | String |Must be one of the existing store names. The store names are initially already defined in* stores.php* configuration file. | Name of the store. |

## Dependencies
This file has the following dependencies:

*     [shipment.csv](/docs/scos/dev/data-import/{{page.version}}/data-import-categories/commerce-setup/file-details-shipment.csv.html)
*     *stores.php* configuration file of demo shop PHP project

## Import template file and content example
A template and an example *shipment_method_store.csv* file can be downloaded here:

| File | Description |
| --- | --- |
| [shipment_method_store.csv template](https://spryker.s3.eu-central-1.amazonaws.com/docs/Developer+Guide/Back-End/Data+Manipulation/Data+Ingestion/Data+Import/Data+Import+Categories/Commerce+Setup/Template+shipment_method_store.csv) | Shipment Method Store .csv template file (empty content, contains headers only). |
| [shipment_method_store.csv](https://spryker.s3.eu-central-1.amazonaws.com/docs/Developer+Guide/Back-End/Data+Manipulation/Data+Ingestion/Data+Import/Data+Import+Categories/Commerce+Setup/shipment_method_store.csv) | Shipment Method Store .csv file containing a Demo Shop data sample. |
