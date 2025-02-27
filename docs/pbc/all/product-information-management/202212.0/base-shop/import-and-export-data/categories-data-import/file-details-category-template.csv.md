---
title: File details - category_template.csv
last_updated: Jun 16, 2021
template: data-import-template
originalLink: https://documentation.spryker.com/2021080/docs/file-details-category-templatecsv
originalArticleId: fac13464-5ddc-4b2a-8dff-f257e196e222
redirect_from:
  - /2021080/docs/file-details-category-templatecsv
  - /2021080/docs/en/file-details-category-templatecsv
  - /docs/file-details-category-templatecsv
  - /docs/en/file-details-category-templatecsv
  - /docs/scos/dev/data-import/201811.0/data-import-categories/catalog-setup/categories/file-details-category-template.csv.html
  - /docs/scos/dev/data-import/201903.0/data-import-categories/catalog-setup/categories/file-details-category-template.csv.html
  - /docs/scos/dev/data-import/201907.0/data-import-categories/catalog-setup/categories/file-details-category-template.csv.html
  - /docs/scos/dev/data-import/202212.0/data-import-categories/catalog-setup/categories/file-details-category-template.csv.html
related:
  - title: Execution order of data importers in Demo Shop
    link: docs/scos/dev/data-import/page.version/demo-shop-data-import/execution-order-of-data-importers-in-demo-shop.html
---

This document describes the `category_template.csv` file to configure category templates in your Spryker shop.

## Import file parameters

| PARAMETER | REQUIRED | TYPE |  REQUIREMENTS OR COMMENTS | DESCRIPTION |
| --- | --- | --- | --- | --- |
| template_name | &check; | String |   | Name of the category template. |
| template_path | &check; | String |   | Must be a valid path to a twig file and it is a unique field, for example, the file cannot have more than one line with the same template path. | Path of the category template. |


## Import template file and content example


| FILE | DESCRIPTION |
| --- | --- |
| [category_template.csv template](https://spryker.s3.eu-central-1.amazonaws.com/docs/Developer+Guide/Back-End/Data+Manipulation/Data+Ingestion/Data+Import/Data+Import+Categories/Catalog+Setup/Categories/Template+category_template.csv) | Exemplary import file with headers only. |
| [category_template.csv](https://spryker.s3.eu-central-1.amazonaws.com/docs/Developer+Guide/Back-End/Data+Manipulation/Data+Ingestion/Data+Import/Data+Import+Categories/Catalog+Setup/Categories/category_template.csv) | Exemplary import file with Demo Shop data. |

## Import command


```bash
data:import:category-template
```
