# Metrics Gold - 0.91

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

-----------------------------------------------------

## Threshold = 0.91

* thr_0.91: 12 axioms (5 classes; 0 subClassOf; 1 relation properties; 8 datatype properties)
  
|Class|Property|Object|
|-----|---------|------|
|Customer(CustomerID)|customerID|customerID|
|Customer(CustomerID)|nameCountry|Country|
|Product(StockCode)|stockCode|StockCode|
|Product(StockCode)|descriptionProduct|Description|
|Product(StockCode)|nameCountry|Country|
|UnitPrice|price|UnitPrice|
|UnitPrice|nameCountry|Country|
|Quantity|quantity|Quantity|
|Quantity|nameCountry|Country|
|Invoice(InvoiceNo)|invoiceNo|InvoiceNo|
|Invoice(InvoiceNo)|invoiceDate|InvoiceDate|
|Invoice(InvoiceNo)|**hasCustomer**|Customer|

-----------------------------------------------------

## Alignment

|Gold | Threshold 0.91|Score|
|-----|--------------|-----|
|Country, nameCountry, Country||0.0|
|Customer, customerID, customerID|Customer,customerID, customerID|1.0|
|Customer,**hasCountry**,Country|Customer, nameCountry, Country|0.5|
|Product, stockCode, StockCode|Product, stockCode, StockCode|1.0|
|Product, descriptionProduct, Description|Product, descriptionProduct, Description|1.0|
|SalesSpecification, price, UnitPrice||0.0|
|SalesSpecification, quantity, Quantity||0.0|
|SalesArticle, **PriceSpecification**, SalesSpecification||0.0|
|SalesArticle, **hasProduct**, Product||0.0|
|Invoice, invoiceNo, InvoiceNo|Invoice, invoiceNo, InvoiceNo|1.0|
|Invoice, invoiceDate, InvoiceDate|Invoice, invoiceDate, InvoiceDate|1.0|
|Invoice, **hasCustomer**, Customer|Invoice, **hasCustomer**, Customer|1.0|
|Invoice, **hasSalesArticle**, SalesArticle||0.0|
||Product, nameCountry, Country|0.0|
||UnitPrice, price, UnitPrice|0.0|
||UnitPrice, nameCountry, Country|0.0|
||Quantity, quantity, Quantity|0.0|
||Quantity, nameCountry, Country|0.0|

## Metrics

* $Precision = 6.5 / 12 = 0.542$
* $Recall = 6.5 / 13 = 0.500$
* $F1 = (2 * 0.542 * 0.500) / (0.542 + 0.500) = 0.520$
* $Class\_cov = 3 / (6 + 2) = 0.375$
* $Rel\_cov = 1 / 5 = 0.200$
* $Dat\_cov = 8 / 8 = 1.0$
* $Global\_cov = 12 / (8 + 5 + 8) = 0.571$
