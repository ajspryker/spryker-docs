---
title: File details- product_price.csv
last_updated: Sep 14, 2020
template: data-import-template
originalLink: https://documentation.spryker.com/v5/docs/file-details-product-pricecsv
originalArticleId: 8a8d6a9b-7783-4acf-8c42-e20edb874472
redirect_from:
  - /v5/docs/file-details-product-pricecsv
  - /v5/docs/en/file-details-product-pricecsv
---

This article contains content of the **product_price.csv** file to configure [prices](/docs/scos/user/features/{{page.version}}/prices-feature-overview/prices-feature-overview.html) of the products/services in your Spryker Demo Dhop.

## Import file parameters 
These are the header fields to be included in the .csv file:

| Field Name | Mandatory | Type | Other Requirements/Comments | Description |
| --- | --- | --- | --- | --- |
| **abstract_sku** | Yes (if `concrete_sku` is empty) | String |Either this field or `concrete_sku` needs to be filled. | SKU of the abstract product to which the price should apply. |
| **concrete_sku** | Yes (if `abstract_sku` is empty) | String |Either this field or `abstract_sku` needs to be filled. | SKU of the concrete product to which the price should apply. |
| **price_type** | No | String |N/A* | Defines the price type. |
| **store** | Yes | String |N/A | Store to which this price should apply. |
| **currency** | No | String |N/A | Defines in which currency the price is. |
| **value_net** | No | Integer |N/A | Sets the net price. |
| **value_gross** | No | Integer |N/A | Sets the gross price. |
| **price_data.volume_prices** | No | String |N/A | Price data which can be used to define alternative prices, i.e volume prices, overwriting  the given net or gross price values. |
*N/A: Not applicable.

## Dependencies

This file has the following dependencies:

* [product_abstract.csv](/docs/scos/dev/data-import/{{page.version}}/data-import-categories/catalog-setup/products/file-details-product-abstract.csv.html)
* [product_concrete.csv](/docs/scos/dev/data-import/{{page.version}}/data-import-categories/catalog-setup/products/file-details-product-concrete.csv.html)
*     *stores.php* configuration file of the Demo Shop PHP project

## Import template file and content example
A template and an example of the *product_price.csv*  file can be downloaded here:

| File | Description |
| --- | --- |
| [product_price.csv template](https://spryker.s3.eu-central-1.amazonaws.com/docs/Developer+Guide/Back-End/Data+Manipulation/Data+Ingestion/Data+Import/Data+Import+Categories/Catalog+Setup/Pricing/Template+product_price.csv) | Product Price .csv template file (empty content, contains headers only). |
| [product_price.csv](https://spryker.s3.eu-central-1.amazonaws.com/docs/Developer+Guide/Back-End/Data+Manipulation/Data+Ingestion/Data+Import/Data+Import+Categories/Catalog+Setup/Pricing/product_price.csv) | Product Price .csv file containing a Demo Shop data sample. |
