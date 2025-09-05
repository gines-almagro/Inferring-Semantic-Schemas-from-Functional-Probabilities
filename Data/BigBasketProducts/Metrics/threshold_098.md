# Metrics Gold - Thr_0.98

## Gold standard

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

-----------------------------------------------------

## Threshold = 0.98

* thr_0.98: 11 axioms (3 classes; 0 subClassOf; 2 relation properties; 9 datatype properties)
  
|Class|Property|Object|
|-----|---------|------|
|SubCategory|subCategoryName|SubCategory|
|SubCategory|belongsToCategory|Category|
|Product(ProductName)|productName|ProductName|
|Product(ProductName)|brandName|Brand|
|Product|**belongsToSubCategory**|SubCategory|
|SalesArticle(Absolute_url)|hasUrl|Absolute_url|
|SalesArticle(Absolute_url)|hasImageUrl|Image_url|
|SalesArticle(Absolute_url)|hasProductQuantity|Quantity|
|SalesArticle(Absolute_url)|priceArticle|Price|
|SalesArticle(Absolute_url)|DiscountPrice|DiscountPrice|
|SalesArticle(Absolute_url)|**hasProduct**|Product|

-----------------------------------------------------

## Alignment

|Gold | Threshold 0.98|Score|
|-----|--------------|-----|
|Category, categoryName, Category| | 0.0|
|SubCategory, subCategoryName, SubCategory|SubCategory, subCategoryName, SubCategory| 1.0|
|SubCategory, **subClassOf**, Category|SubCategory, belongsToCategory, Category| 0.5|
|Product, productName, ProductName|Product, productName, ProductName|1.0|
|Product, brandName, Brand|Product, brandName, Brand|1.0|
|SalesSpecification, priceArticle, Price||0.0|
|SalesSpecification, discountPrice, DiscountPrice||0.0|
|SalesArticle, hasUrl, Absolute_url|SalesArticle, hasUrl, Absolute_url|1.0|
|SalesArticle, hasImageUrl, Image_url|SalesArticle, hasImageUrl, Image_url|1.0|
|SalesArticle, hasProductQuantity, Quantity|SalesArticle, hasProductQuantity, Quantity|1.0|
|SalesArticle, **hasProduct**, Product|SalesArticle, **hasProduct**, Product|1.0|
|SalesArticle, **belongsToSubCategory**, SubCategory||0.0|
|SalesArticle, **hasSalesSpecification**, SalesSpecification||0.0|
||Product, **belongsToSubCategory**, SubCategory|0.0|
||SalesArticle, priceArticle, Price|0.0|
||SalesArticle, discountPrice, DiscountPrice|0.0|

## Metrics

* $Precision = 7.5 / 11 = 0.682$
* $Recall = 7.5 / 13 = 0.577$
* $F1 = (2 * 0.682 * 0.577) / (0.682 + 0.577) = 0.625$
* $Class\_cov = 3 / 5 = 0.600$
* $Rel\_cov = 2 / 4 = 0.500$
* $Dat\_cov = 8 / (9 + 1) = 0.800$
* $Global\_cov = 13 / (5 + 4 + 10) = 0.684$
