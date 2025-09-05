# Metrics Gold - 0.96

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

## Threshold = 0.96

* thr_0.96: 7 axioms (3 classes; 0 subClassOf; 1 relation properties; 6 datatype properties)
  
|Class|Property|Object|
|-----|---------|------|
|Customer(CustomerID)|customerID|customerID|
|Customer(CustomerID)|nameCountry|Country|
|Product(StockCode)|stockCode|StockCode|
|Product(StockCode)|descriptionProduct|Description|
|Invoice(InvoiceNo)|invoiceNo|InvoiceNo|
|Invoice(InvoiceNo)|invoiceDate|InvoiceDate|
|Invoice(InvoiceNo)|**hasCustomer**|Customer|

-----------------------------------------------------

## Alignment

|Gold | Threshold 0.96|Score|
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

## Metrics

* $Precision = 6.5 / 7 = 0.929$
* $Recall = 6.5 / 13 = 0.500$
* $F1 = (2 * 0.929 * 0.500) / (0.929 + 0.500) = 0.650$
* $\text{Class coverage} = 3 / 6 = 0.500$
* $\text{Relation coverage} = 1 / 5 = 0.200$
* $\text{Datatype coverage} = 6 / 8 = 0.750$
* $\text{Global coverage} = 10 / (6 + 5 + 8) = 0.526$
