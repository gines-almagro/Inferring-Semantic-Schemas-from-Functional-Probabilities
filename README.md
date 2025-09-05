# Inferring Semantic Schemas from Functional Probabilities

## BigBasket Products

[processed_BigBasket.csv (2.57 MB)](./Data/BigBasketProducts/processed_BigBasket.csv)

* Initial structure: 8208 rows x 9 columns
* Final structure: 8208 rows x 9 columns
* Processing:
  * Remove duplicate rows
  * Remove rows with all null values

  |Columns Name | Datatypes | NoNull | Unique |
  |--|--|--|--|
  |ProductName | string | 8208 | 6769 |
  | Brand | string | 8208 | 842 |
  | Price | float | 8208 | 1043 |
  | DiscountPrice | float | 8208 | 2180 |
  | Image\_Url | anyURI | 8208 | 8202 |
  | Quantity | string | 8208 | 781 |
  | Category | string | 8208 | 11 |
  | SubCategory | string | 8208 | 334 |
  | Absolute\_Url | anyURI | 8208 | 8208 |

Threshold = 1

* [BigBasket schema 1.0](./Data/BigBasketProducts/Results/processed_BigBasket_1.0_0_schema.csv)
* [BigBasket probability 1.0](./Data/BigBasketProducts/Results/processed_BigBasket_1.0_0_fd_prob.csv)
* [BigBasket quality 1.0](./Data/BigBasketProducts/Results/processed_BigBasket_1.0_0_fd_ratios.csv)

Threshold = 0.99

* [BigBasket schema 0.99](./Data/BigBasketProducts/Results/processed_BigBasket_0.99_0_schema.csv)
* [BigBasket probability 0.99](./Data/BigBasketProducts/Results/processed_BigBasket_0.99_0_fd_prob.csv)
* [BigBasket quality 0.99](./Data/BigBasketProducts/Results/processed_BigBasket_0.99_0_fd_ratios.csv)

Threshold = 0.98

* [BigBasket schema 0.98](./Data/BigBasketProducts/Results/processed_BigBasket_0.98_0_schema.csv)
* [BigBasket probability 0.98](./Data/BigBasketProducts/Results/processed_BigBasket_0.98_0_fd_prob.csv)
* [BigBasket quality 0.98](./Data/BigBasketProducts/Results/processed_BigBasket_0.98_0_fd_ratios.csv)

Threshold = 0.93

* [BigBasket schema 0.93](./Data/BigBasketProducts/Results/processed_BigBasket_0.93_0_schema.csv)
* [BigBasket probability 0.93](./Data/BigBasketProducts/Results/processed_BigBasket_0.93_0_fd_prob.csv)
* [BigBasket quality 0.93](./Data/BigBasketProducts/Results/processed_BigBasket_0.93_0_fd_ratios.csv)

## Ecommerce Data

[processed_data.csv (43.1 MB)](./Data/EcommerceData/processed_data.csv)

* Initial structure: 541909 rows x 8 columns
* Final structure: 530652 rows x 8 columns
* Processing:
  * Remove duplicate rows
  * Remove rows with all null values
  * Remove rows starting with '"'

|Columns Name | Datatypes | NoNull | Unique |
|--|--|--|--|
| InvoiceNo | string | 530652 | 25858 |
| StockCode | string | 530652 | 3999 |
| Description | string | 529198 | 4113 |
| Quantity | integer | 530652 | 709 |
| InvoiceDate | dataTime | 530652 | 23225 |
| UnitPrice | float | 530652 | 1628 |
| CustomerID | integer | 398005 | 4370 |
| Country | string | 530652 | 38 |

## Gold standard

* Gold: 13 axioms (6 classes; 0 subClassOf; 5 relation properties; 8 datatype properties)
  
|Class|Property|Object|
|-----|---------|------|
|Country|nameCountry|Country|
|Customer(CustomerID)|customerID|customerID|
|Customer(CustomerID)|**hasCountry**|Country|
|Product(StockCode)|stockCode|StockCode|
|Product(StockCode)|descriptionProduct|Description|
|SalesSpecification(Quantity_UnitPrice)|price|UnitPrice|
|SalesSpecification(Quantity_UnitPrice)|quantity|Quantity|
|SalesArticle(InvoiceNo_StockCode)|**PriceSpecification**|SalesSpecification|
|SalesArticle(InvoiceNo_StockCode)|**hasProduct**|Product|
|Invoice(InvoiceNo)|invoiceNo|InvoiceNo|
|Invoice(InvoiceNo)|invoiceDate|InvoiceDate|
|Invoice(InvoiceNo)|**hasCustomer**|Customer|
|Invoice(InvoiceNo)|**hasSalesArticle**|SalesArticle|

[Threshold 1.0](../)