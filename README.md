# Inferring Semantic Schemas from Functional Probabilities

## BigBasket Products

### Dataset BigBasket

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

### Results BigBasket

Threshold = 1.0

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

### Metrics BigBasket

Gold Standard

* Gold: 13 axioms (5 classes; 1 subClassOf; 3 relation properties; 9 datatype properties)
  
|Class|Property|Object|
|-----|---------|------|
|Category|categoryName|Category|
|SubCategory|subCategoryName|SubCategory|
|SubCategory|**subClassOf**|Category|
|Product(ProductName)|productName|ProductName|
|Product(ProductName)|brandName|Brand|
|SalesSpecification(Price_DiscountPrice)|priceArticle|Price|
|SalesSpecification(Price_DiscountPrice)|DiscountPrice|DiscountPrice|
|SalesArticle(Absolute_url)|hasUrl|Absolute_url|
|SalesArticle(Absolute_url)|hasImageUrl|Image_url|
|SalesArticle(Absolute_url)|hasProductQuantity|Quantity|
|SalesArticle(Absolute_url)|**hasProduct**|Product|
|SalesArticle(Absolute_url)|**belongsToSubCategory**|SubCategory|
|SalesArticle(Absolute_url)|**hasSalesSpecification**|SalesSpecification|

Threshold = 1.0

* [BigBasket metrics 1.0](./Data/BigBasketProducts/Metrics/threshold_1.md)

* $Precision = 5.5 / 12 = 0.458$
* $Recall = 5.5 / 13 = 0.423$
* $F1 = (2 * 0.458 * 0.423) / (0.458 + 0.423) = 0.440$
* $\text{Class coverage} = 2 / (5 + 1) = 0.333$
* $\text{Relation coverage} = 1 / (4 + 1) = 0.200$
* $\text{Datatype coverage} = 8 / (9 + 1) = 0.800$
* $\text{Global coverage} = 11 / (6 + 5 + 10) = 0.524$

Threshold = 0.99

* [BigBasket metrics 0.99](./Data/BigBasketProducts/Metrics/threshold_099.md)

* $Precision = 6.5 / 11 = 0.591$
* $Recall = 6.5 / 13 = 0.500$
* $F1 = (2 * 0.591 * 0.500) / (0.591 + 0.500) = 0.542$
* $\text{Class coverage} = 3 / 5 = 0.600$
* $\text{Relation coverage} = 2 / 4 = 0.500$
* $\text{Datatype coverage} = 8 / (9 + 1) = 0.800$
* $\text{Global coverage} = 13 / (5 + 4 + 10) = 0.684$

Threshold = 0.98

* [BigBasket metrics 0.98](./Data/BigBasketProducts/Metrics/threshold_098.md)

* $Precision = 7.5 / 11 = 0.682$
* $Recall = 7.5 / 13 = 0.577$
* $F1 = (2 * 0.682 * 0.577) / (0.682 + 0.577) = 0.625$
* $\text{Class coverage} = 3 / 5 = 0.600$
* $\text{Relation coverage} = 2 / 4 = 0.500$
* $\text{Datatype coverage} = 8 / (9 + 1) = 0.800$
* $\text{Global coverage} = 13 / (5 + 4 + 10) = 0.684$

Threshold = 0.93

* [BigBasket metrics 0.93](./Data/BigBasketProducts/Metrics/threshold_093.md)
  
* $Precision = 7 / 13 = 0.538$
* $Recall = 7 / 13 = 0.538$
* $F1 = (2 * 0.538 * 0.538) / (0.538 + 0.538) = 0.538$
* $\text{Class coverage} = 3 / (5 + 1) = 0.500$
* $\text{Relation coverage} = 2 / (4 + 1) = 0.400$
* $\text{Datatype coverage} = 8 / (9 + 1) = 0.800$
* $\text{Global coverage} = 13 / (6 + 5 + 10) = 0.619$

## Ecommerce Data

### Dataset Ecommerce

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

### Results Ecommerce

Threshold = 1.0

* [Ecommerce schema 1.0](./Data/EcommerceData/Results/processed_data_1.0_0_schema.csv)
* [Ecommerce probability 1.0](./Data/EcommerceData/Results/processed_data_1.0_0_fd_prob.csv)
* [Ecommerce quality 1.0](./Data/EcommerceData/Results/processed_data_1.0_0_fd_ratios.csv)

Threshold = 0.99

* [Ecommerce schema 0.99](./Data/EcommerceData/Results/processed_data_0.99_0_schema.csv)
* [Ecommerce probability 0.99](./Data/EcommerceData/Results/processed_data_0.99_0_fd_prob.csv)
* [Ecommerce quality 0.99](./Data/EcommerceData/Results/processed_data_0.99_0_fd_ratios.csv)

Threshold = 0.96

* [Ecommerce schema 0.96](./Data/EcommerceData/Results/processed_data_0.96_0_schema.csv)
* [Ecommerce probability 0.96](./Data/EcommerceData/Results/processed_data_0.96_0_fd_prob.csv)
* [Ecommerce quality 0.96](./Data/EcommerceData/Results/processed_data_0.96_0_fd_ratios.csv)

Threshold = 0.91

* [Ecommerce schema 0.91](./Data/EcommerceData/Results/processed_data_0.91_0_schema.csv)
* [Ecommerce probability 0.91](./Data/EcommerceData/Results/processed_data_0.91_0_fd_prob.csv)
* [Ecommerce quality 0.91](./Data/EcommerceData/Results/processed_data_0.91_0_fd_ratios.csv)

### Metrics Ecommerce

Gold standard

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

Threshold = 1.0

[Ecommerce Metrics 1.0](./Data/EcommerceData/Metrics/threshold_1.md)

