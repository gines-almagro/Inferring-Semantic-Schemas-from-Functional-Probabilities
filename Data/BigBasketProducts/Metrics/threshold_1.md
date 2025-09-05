# Metrics Gold - Thr_1

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

## Threshold = 1.0

* thr_1: 12 axioms (3 classes; 0 subClassOf; 2 relation properties; 9 datatype properties)
  
|Class|Property|Object|
|-----|---------|------|
|SubCategory|subCategoryName|SubCategory|
|SubCategory|belongsToCategory|Category|
|ImageArticle(Image_url)|hasImageUrl|Image_url|
|ImageArticle(Image_url)|belongsToCategory|Category|
|SalesArticle(Absolute_url)|hasUrl|Absolute_url|
|SalesArticle(Absolute_url)|hasProductQuantity|Quantity|
|SalesArticle(Absolute_url)|productName|ProductName|
|SalesArticle(Absolute_url)|brandName|Brand|
|SalesArticle(Absolute_url)|priceArticle|Price|
|SalesArticle(Absolute_url)|DiscountPrice|DiscountPrice|
|SalesArticle(Absolute_url)|**hasImageArticle**|ImageArticle|
|SalesArticle(Absolute_url)|**belongsToSubCategory**|SubCategory|

-----------------------------------------------------

## Alignment

|Gold | Threshold 1.0|Score|
|-----|--------------|-----|
|Category, categoryName, Category| | 0.0|
|SubCategory, subCategoryName, SubCategory|SubCategory, subCategoryName, SubCategory| 1.0|
|SubCategory, **subClassOf**, Category|SubCategory, belongsToCategory, Category| 0.5|
|Product, productName, ProductName||0.0|
|Product, brandName, Brand||0.0|
|SalesSpecification, priceArticle, Price||0.0|
|SalesSpecification, DiscountPrice, DiscountPrice||0.0|
|SalesArticle, hasUrl, Absolute_url|SalesArticle, hasUrl, Absolute_url|1.0|
|SalesArticle, hasImageUrl, Image_url|SalesArticle, **hasImageArticle**, ImageArticle|0.5|
|SalesArticle, hasProductQuantity, Quantity|SalesArticle, hasProductQuantity, Quantity|1.0|
|SalesArticle, **hasProduct**, Product|SalesArticle, productName, ProductName|0.5|
|SalesArticle, **belongsToSubCategory**, SubCategory|SalesArticle, **belongsToSubCategory**, SubCategory|1.0|
|SalesArticle, **hasSalesSpecification**, SalesSpecification||0.0|
||SalesArticle, brandName, Brand|0.0|
||SalesArticle, priceArticle, Price|0.0|
||SalesArticle, DiscountPrice, DiscountPrice|0.0|
||ImageArticle, hasImageUrl, Image_url|0.0 
||ImageArticle, belongsToCategory, Category|0.0|

## Metrics

* $Precision = 5.5 / 12 = 0.458$
* $Recall = 5.5 / 13 = 0.423$
* $F1 = (2 * 0.458 * 0.423) / (0.458 + 0.423) = 0.440$
* $Class coverage = 2 / (5 + 1) = 0.333$
* $Relation coverage = 1 / (4 + 1) = 0.200$
* $Datatype coverage = 8 / (9 + 1) = 0.800$
* $Global coverage = 11 / (6 + 5 + 10) = 0.524$
