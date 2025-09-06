# Metrics Gold - Thr_0.93

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

## Threshold = 0.93

* thr_0.93: 13 axioms (4 classes; 0 subClassOf; 3 relation properties; 9 datatype properties)
  
|Class|Property|Object|
|-----|---------|------|
|SubCategory|subCategoryName|SubCategory|
|SubCategory|belongsToCategory|Category|
|Brand|brandName|Brand|
|Brand|belongsToCategory|Category|
|Product(ProductName)|productName|ProductName|
|Product(ProductName)|**hasBrand**|Brand|
|Product(ProductName)|**belongsToSubCategory**|SubCategory|
|SalesArticle(Absolute_url)|hasUrl|Absolute_url|
|SalesArticle(Absolute_url)|hasImageUrl|Image_url|
|SalesArticle(Absolute_url)|hasProductQuantity|Quantity|
|SalesArticle(Absolute_url)|priceArticle|Price|
|SalesArticle(Absolute_url)|discountPrice|DiscountPrice|
|SalesArticle(Absolute_url)|**hasProduct**|Product|

-----------------------------------------------------

## Alignment

|Gold | Threshold 0.93|Score|
|-----|--------------|-----|
|Category, categoryName, Category| | 0.0|
|SubCategory, subCategoryName, SubCategory|SubCategory, subCategoryName, SubCategory| 1.0|
|SubCategory, **subClassOf**, Category|SubCategory, belongsToCategory, Category| 0.5|
|Product, productName, ProductName|Product, productName, ProductName|1.0|
|Product, brandName, Brand|Product, **hasBrand**, Brand|0.5|
|SalesSpecification, priceArticle, Price||0.0|
|SalesSpecification, discountPrice, DiscountPrice||0.0|
|SalesArticle, hasUrl, Absolute_url|SalesArticle, hasUrl, Absolute_url|1.0|
|SalesArticle, hasImageUrl, Image_url|SalesArticle, hasImageUrl, Image_url|1.0|
|SalesArticle, hasProductQuantity, Quantity|SalesArticle, hasProductQuantity, Quantity|1.0|
|SalesArticle, **hasProduct**, Product|SalesArticle, **hasProduct**, Product|1.0|
|SalesArticle, **belongsToSubCategory**, SubCategory||0.0|
|SalesArticle, **hasSalesSpecification**, SalesSpecification||0.0|
||Brand, brandName, Brand|0.0|
||Brand, belongsToCategory, Category|0.0|
||Product, **belongsToSubCategory**, SubCategory|0.0|
||SalesArticle, priceArticle, Price|0.0|
||SalesArticle, discountPrice, DiscountPrice|0.0|

## Metrics

* $Precision = 7 / 13 = 0.538$
* $Recall = 7 / 13 = 0.538$
* $F1 = (2 * 0.538 * 0.538) / (0.538 + 0.538) = 0.538$
* $\text{Class coverage} = 3 / (5 + 1) = 0.500$
* $\text{Relation coverage} = 2 / (4 + 1) = 0.400$
* $\text{Datatype coverage} = 8 / (9 + 1) = 0.800$
* $\text{Global coverage} = 13 / (6 + 5 + 10) = 0.619$
