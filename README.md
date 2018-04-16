# Ceneo XML PrestaShop module

Ceneo XML PrestaShop module generates valid xml with shop offers, which can be easily integrated with Ceneo price compariser.

## Documentation links

* [Ceneo XML PrestaShop module installation documentation (in Polish)](https://www.ceneo.pl/poradniki/Podrecznik-integracji-platformy-prestashop)
* [Ceneo XML file structure documentation (in Polish)](https://shops.ceneo.pl/documents/Informacje%20na%20temat%20struktury%20pliku%20xml.pdf)
* [PrestaShop documentation for developers](https://developers.prestashop.com/)

## Developers guide
### How does it work?

Ceneo XML PrestaShop module selects data about valid products from PrestaShop store db and generates xml, which is displayed under specific url.

### Module constraints
* It's dedicated to 1.5.x.x and 1.6.x.x versions of PrestaShop
* Currently supports only Polish language
* Does not support Multistore

### Module classes description
* ***ceneoxml.php*** - main module class

* ***classes/AvailabilityEnum.php*** - product availability enum
* ***classes/CategoryPathInfo.php*** - returns product category path info
* ***classes/CeneoConfig.php*** - configuration values connected with ceneo xml constraints
* ***classes/CeneoXmlWriter.php*** - ceneo xml elements writer
* ***classes/FeatureEnum.php*** - feature enum
* ***classes/UrlProviderFactory.php*** - provides proper product Url, which differs depending on PrestaShop version 

* ***controllers/front/xml.php*** - controller responsible for displaying page with generated xml under specific url

* ***helpers/builders/ArrayBuilders/*** - helper builders responsible for creating data arrays
* ***helpers/builders/CeneoXmlBuilder.php*** - xml builder
* ***helpers/calculators/PriceCalculator.php*** - calculator responsible for calculating final price, which depends on specific factors
* ***helpers/providers/AvailabilityStatusProvider.php*** - product availability status provider
* ***helpers/providers/UrlProvider_x_x.php*** - provides product url for specific PrestaShop version
* ***helpers/providers/UrlProviderBase.php*** - base class for UrlProviders
* ***helpers/providers/UrlProviderFactory.php*** - factory which returns specific UrlProvider, depending on PrestaShop version
* ***helpers/CategoryHelper.php*** - helper methods connected with categories
* ***helpers/PrestaShopHelper.php*** - helper methods connected stricly with PrestaShop engine

* ***repositories/providers/SqlQueryProvider_x_x.php*** - sql queries for specific PrestaShop version
* ***repositories/providers/SqlQueryProviderBase.php*** - common sql queries
* ***repositories/providers/SqlQueryProviderFactory.php*** - factory which returns specific SqlQueryProvider, depending on PrestaShop version
* ***repositories/PrestaShopRepository.php*** - main repository for PrestaShop data

* ***tests*** - unit tests for module classes
