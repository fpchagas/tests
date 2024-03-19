# Purchase Order Reporting View
# View: VendorPerformance
---
## Overview
This view provides a comprehensive overview of purchase orders, goods receipts, and vendor scorecards based on historical and current data from the SAP system.
## Data Sources
| Table | Name | Description |
|---|---|---|
| PurchaseDocuments | PurchaseDocuments | This table contains header-level information about purchase orders, such as order number, vendor, material, quantity, and value. |
| PurchaseOrdersGoodsReceipt | PurchaseOrdersGoodsReceipt | This table contains information about goods receipts, such as goods receipt date, quantity, and value. |
| PurchaseOrdersInvoiceReceipt | PurchaseOrdersInvoiceReceipt | This table contains information about invoice receipts, such as invoice date, quantity, and value. |
| PurchasingOrganizationsMD | PurchasingOrganizationsMD | This table contains master data about purchasing organizations, such as name and address. |
| PurchasingGroupsMD | PurchasingGroupsMD | This table contains master data about purchasing groups, such as name and description. |
| VendorsMD | VendorsMD | This table contains master data about vendors, such as name, address, and contact information. |
| CompaniesMD | CompaniesMD | This table contains master data about companies, such as name and address. |
| MaterialsMD | MaterialsMD | This table contains master data about materials, such as material number, description, and material type. |
| MaterialTypesMD | MaterialTypesMD | This table contains master data about material types, such as description. |
| CurrencyConversion | CurrencyConversion | This table contains currency conversion rates. |
| LanguageKey | LanguageKey | This table contains the language key for the current user. |

## Use Cases
| Use Case | Description |
|---|---|
| Purchase Order Analysis | This view can be used to analyze purchase orders, track vendor performance, and identify areas for improvement. |
| Goods Receipt Analysis | This view can be used to analyze goods receipts, identify delays, and improve vendor performance. |
| Vendor Scorecarding | This view can be used to create vendor scorecards that measure vendor performance on key metrics such as delivery time, quality, and price. |
| Material Spend Analysis | This view can be used to analyze material spend, identify cost savings opportunities, and negotiate better prices with vendors. |
| Inventory Management | This view can be used to monitor inventory levels, identify stockouts, and optimize inventory management. |

## Query Logic
The query logic for this view is based on a join between the PurchaseDocuments, PurchaseOrdersGoodsReceipt, and PurchaseOrdersInvoiceReceipt tables. The join is performed on the DocumentNumber_EBELN field, which is the unique identifier for purchase orders. The query also includes joins to the PurchasingOrganizationsMD, PurchasingGroupsMD, VendorsMD, CompaniesMD, MaterialsMD, MaterialTypesMD, CurrencyConversion, and LanguageKey tables to provide additional information about purchasing organizations, purchasing groups, vendors, companies, materials, material types, currency conversion rates, and the current user's language.


## SAP Standard Related Transactions
| Transaction Code | Description |
|---|---|
| ME21N | Create Purchase Order |
| ME22N | Change Purchase Order |
| ME23N | Display Purchase Order |
| MIGO | Goods Receipt |
| MIRO | Invoice Receipt |
| XK01 | Create Vendor |
| XK02 | Change Vendor |
| XK03 | Display Vendor |

## Considerations
### Data Currency
The data in this view is stored in the currency of the purchase order. When comparing data from different purchase orders, it is important to consider the exchange rates at the time of the order.
### Data Accuracy
The data in this view is only as accurate as the data in the underlying SAP tables. It is important to ensure that the SAP tables are updated regularly and that the data is validated before using it for analysis.
### Data Volume
This view can contain a large amount of data, especially if it includes data from a long period of time. It is important to consider the performance implications of using this view in reports and dashboards.
