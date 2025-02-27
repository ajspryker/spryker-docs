---
title: "Import file details: merchant_oms_process.csv"
last_updated: Jun 07, 2021
description: This document describes the merchant_oms_process.csv file to configure Merchant state machines in your Spryker shop.
template: import-file-template
redirect_from:
  - /docs/pbc/all/order-management-system/202212.0/marketplace/import-data/file-details-merchant_oms_process.csv.html
related:
  - title: Merchant Oms
    link: docs/marketplace/dev/feature-walkthroughs/page.version/marketplace-order-management-feature-walkthrough/merchant-oms.html
  - title: Marketplace and merchant state machines overview
    link: docs/marketplace/user/features/page.version/marketplace-order-management-feature-overview/marketplace-and-merchant-state-machines-overview/marketplace-and-merchant-state-machines-overview.html
  - title: Execution order of data importers in Demo Shop
    link: docs/scos/dev/data-import/page.version/demo-shop-data-import/execution-order-of-data-importers-in-demo-shop.html
---

This document describes the `merchant_oms_process.csv` file to configure [Merchant state machines](/docs/pbc/all/order-management-system/{{page.version}}/marketplace/marketplace-order-management-feature-overview/marketplace-and-merchant-state-machines-overview/marketplace-and-merchant-state-machines-overview.html#merchant-state-machine) in your Spryker shop.

## Import file dependencies

[merchant.csv](/docs/pbc/all/merchant-management/{{site.version}}/marketplace/import-data/file-details-merchant.csv.html)


## Import file parameters


| PARAMETER  | REQUIRED | TYPE | DEFAULT VALUE | REQUIREMENTS OR COMMENTS | DESCRIPTION   |
| --------------- | ---------- | ------- | ------------ | -------------- | ----------------------- |
| merchant_reference        | &check;             | String   |                   | Unique                       | Identifier of the merchant in the system. |
| merchant_oms_process_name | &check;             | String   |                   |                              | Name of the merchant state machine.       |


## Import template file and content example

| FILE         | DESCRIPTION       |
| ------------------------ | ------------------------ |
| [template_merchant_oms_process.csv](https://spryker.s3.eu-central-1.amazonaws.com/docs/Developer+Guide/Back-End/Data+Manipulation/Data+Ingestion/Data+Import/Data+Import+Categories/Marketplace+setup/template_merchant_oms_process.csv) | Import file template with headers only.         |
| [merchant_oms_process.csv](https://spryker.s3.eu-central-1.amazonaws.com/docs/Developer+Guide/Back-End/Data+Manipulation/Data+Ingestion/Data+Import/Data+Import+Categories/Marketplace+setup/merchant_oms_process.csv) | Example of the import file with Demo Shop data. |

## Import command

```bash
data:import merchant-oms-process
```
