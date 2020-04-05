# Magento 2 Questions Answer for Developer
## Use of search_request.xml
Magento 2 provides a declarative way to describe search request which should be executed. search_request.xml is a part of Query API. 

---
## Use of di.xml
- We can use di.xml for ( rewrite ) preference of a particular class.
- We can send new or replace the existing class [arguments](https://magento.stackexchange.com/questions/103606/what-are-all-the-allowed-xsitype-values-in-the-xmls-from-magento2).
- Use plugins to do some stuff before, after and around the function
- By using virtualTypes creating a sub-class of another class.

Let us take a quick example from Magento 2 customer module.

##1.Preference
	`<preference for="Magento\Customer\Api\AddressRepositoryInterface" type="Magento\Customer\Model\ResourceModel\AddressRepository" />`

Above code, When someone asks you to instantiate a `Magento\Customer\Api\AddressRepositoryInterface` it will instantiate a `Magento\Customer\Model\ResourceModel\AddressRepository` object (the type attribute).

Class preference configuration is not just for interfaces we can change the actual classes as well.

	`<preference for="Magento\Customer\Model\CustomerManagement" type="Magento\Customer\Model\customModel" />`

You can create 'customModel' class for 'CustomerManagement' and do the changes. Class preference system as a replacement for the class rewrite system.

[Magento 2 Object Manager Preferences](http://alanstorm.com/magento_2_object_manager_preferences)




---

[![Alt text](https://www.kashyapsoftware.com/pub/media/logo/stores/1/ks_logo.png "kashyapsoftware.com")](https://www.kashyapsoftware.com/)

