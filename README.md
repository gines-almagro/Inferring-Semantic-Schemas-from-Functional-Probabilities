# Inferring Semantic Schemas from Functional Probabilities

## BigBasket Products Metrics



## Ecommerce Data Metrics

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