# Metrics Gold - Thr_1.0

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

## Threshold = 1.0

* thr_1.0: 4 axioms (2 classes; 0 subClassOf; 1 relation properties; 3 datatype properties)
  
|Class|Property|Object|
|-----|---------|------|
|Customer(CustomerID)|customerID|customerID|
|Customer(CustomerID)|nameCountry|Country|
|Invoice(InvoiceNo)|invoiceNo|InvoiceNo|
|Invoice(InvoiceNo)|**hasCustomer**|Customer|

-----------------------------------------------------

## Alignment

|Gold | Threshold 1.0|Score|
|-----|--------------|-----|
|Country, nameCountry, Country||0.0|
|Customer, customerID, customerID|Customer,customerID, customerID|1.0|
|Customer,**hasCountry**,Country|Customer, nameCountry, Country|0.5|
|Product, stockCode, StockCode||0.0|
|Product, descriptionProduct, Description||0.0|
|SalesSpecification, price, UnitPrice||0.0|
|SalesSpecification, quantity, Quantity||0.0|
|SalesArticle, **PriceSpecification**, SalesSpecification||0.0|
|SalesArticle, **hasProduct**, Product||0.0|
|Invoice, invoiceNo, InvoiceNo|Invoice, invoiceNo, InvoiceNo|1.0|
|Invoice, invoiceDate, InvoiceDate||0.0|
|Invoice, **hasCustomer**, Customer|Invoice, **hasCustomer**, Customer|1.0|
|Invoice, **hasSalesArticle**, SalesArticle||0.0|

## Metrics

* $Precision = 3.5 / 4 = 0.875$
* $Recall = 3.5 / 13 = 0.269$
* $F1 = (2 * 0.875 * 0.269) / (0.875 + 0.269) = 0.411$
* $\text{Class coverage} = 2 / 6 = 0.333$
* $\text{Relation coverage} = 1 / 5 = 0.200$
* $\text{Datatype coverage} = 3 / 8 = 0.375$
* $\text{Global coverage} = 6 / (6 + 5 + 8) = 0.316$
