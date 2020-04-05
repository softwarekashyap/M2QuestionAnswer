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

## 1. Preference
`<preference for="Magento\Customer\Api\AddressRepositoryInterface" type="Kashyap\Customer\Model\ResourceModel\AddressRepository" />`

Above code, When someone asks you to instantiate a `Magento\Customer\Api\AddressRepositoryInterface` it will instantiate a `Kashyap\Customer\Model\ResourceModel\AddressRepository` object (the type attribute).

Class preference configuration is not just for interfaces we can change the actual classes as well.

`<preference for="Magento\Customer\Model\CustomerManagement" type="Kashyap\Customer\Model\customModel" />`

You can create 'customModel' class for 'CustomerManagement' and do the changes. Class preference system as a replacement for the class rewrite system.

[Magento 2 Object Manager Preferences](http://alanstorm.com/magento_2_object_manager_preferences)

## 2. Arguments
	<type name="Magento\Customer\Model\ResourceModel\Group" shared="false">
	    <arguments>
	        <argument name="groupManagement" xsi:type="object">Kashyap\Customer\Api\GroupManagementInterface\Proxy</argument>
	    </arguments>
    </type>

In th above code, We are sending object as an argument, we are saying system to insert "Proxy" class as an object with the name of groupManagement. Also, we can use Arguments for replacing the existing argument too.

[Magento 2 Object Manager Argument Replacement](http://alanstorm.com/magento_2_object_manager_argument_replacement)

## 3. Plugin
	<type name="Magento\Customer\Model\ResourceModel\Visitor">
    	<plugin name="catalogLog" type="Kashyap\Catalog\Model\Plugin\Log" />
    </type>
In the above code , `public function clean($object)` in visitor class is called after public function `afterClean(Visitor $subject, $logResourceModel)` which is in Log class

## 4. Virtual Types
Creating a virtual type is sort of like creating a sub-class for an existing class.

For more note please go through the practical examples some I mentioned as links from Alan, by practice you can get more clear experience.

---
## Use of event.xml

[![Alt text](https://www.kashyapsoftware.com/pub/media/logo/stores/1/ks_logo.png "kashyapsoftware.com")](https://www.kashyapsoftware.com/)

