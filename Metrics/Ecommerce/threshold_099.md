# Metrics Gold - Thr_0.99

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

## Threshold = 0.99

* thr_0.99: 9 axioms (4 classes; 0 subClassOf; 2 relation properties; 6 datatype properties)
  
|Class|Property|Object|
|-----|---------|------|
|Customer(CustomerID)|customerID|customerID|
|Customer(CustomerID)|nameCountry|Country|
|Product(Description)|descriptionProduct|Description|
|Product(Description)|stockCode|StockCode|
|InvoiceDate(InvoiceDate)|invoiceDate|InvoiceDate|
|InvoiceDate(InvoiceDate)|nameCountry|Country|
|Invoice(InvoiceNo)|invoiceNo|InvoiceNo|
|Invoice(InvoiceNo)|**hasInvoiceDate**|InvoiceDate|
|Invoice(InvoiceNo)|**hasCustomer**|Customer|

-----------------------------------------------------

## Alignment

|Gold | Threshold 0.99|Score|
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
|Invoice, invoiceDate, InvoiceDate|Invoice, **hasInvoiceDate**, InvoiceDate|0.5|
|Invoice, **hasCustomer**, Customer|Invoice, **hasCustomer**, Customer|1.0|
|Invoice, **hasSalesArticle**, SalesArticle||0.0|
||InvoiceDate, invoiceDate, InvoiceDate|0.0|
||InvoiceDate, nameCountry, Country|0.0|

## Metrics

* $Precision = 6 / 9 = 0.667$
* $Recall = 6 / 13 = 0.462$
* $F1 = (2 * 0.667 * 0.462) / (0.667 + 0.462) = 0.546$
* $\text{Class coverage} = 3 / (6 +1) = 0.429$
* $\text{Relation coverage} = 1 / (5 + 1) = 0.167$
* $\text{Datatype coverage} = 5 / (8 + 1) = 0.556$
* $\text{Global coverage} = 9 / (7 + 6 + 9) = 0.409$
