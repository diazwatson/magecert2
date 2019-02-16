---
layout: archive
title: Customer Management
permalink: /professional-developer/customer-management
---
## 10.1. Demonstrate ability to customize My Account
### How do you add a menu item?
Menu items are defined in `vendor/magento/module-customer/view/frontend/layout/customer_account.xml`

In order to add a new menu we need to overwrite this layout as follow:

```xml
<?xml version="1.0"?>
<!-- App/Code/Vendor/ModuleName/view/frontend/layout/customer-account.xml -->
<page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">
    <body>
        <referenceBlock name="customer_account_navigation">
            <block class="Magento\Customer\Block\Account\SortLinkInterface" name="customer-account-navigation-sample">
                <arguments>
                    <!-- path to the controller in charge of handle the request-->
                    <argument name="path" xsi:type="string">sample</argument>
                    <!-- Label of the menu item --->
                    <argument name="label" xsi:type="string">Sample Menu</argument>
                    <argument name="sortOrder" xsi:type="number">10</argument>
                </arguments>
            </block>
        </referenceBlock>
    </body>
</page>
```


{: .notice--warning}
**Notice** that If you click in the `Sample Menu` item you will be redirected to a 404 page because for that to work we would need a 
controller to handle the request which is out of the scope of this exercise.
{: .notice--warning}


### How do you remove a menu item?
```xml
<?xml version="1.0"?>
<!-- App/Code/Vendor/ModuleName/view/frontend/layout/customer-account.xml -->
<page xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:View/Layout/etc/page_configuration.xsd">
    <body>
        <!-- Reference to the menu item block we want to remove -->
        <referenceBlock name="customer-account-navigation-wish-list-link" remove="true"/>
    </body>
</page>
```

### How would you customize the “Order History” page?
The layout responsible for handle the order history page is `sales_order_history` and is in 
`vendor/magento/module-sales/view/frontend/layout/sales_order_history.xml`

As a simple exercise, lets create a module that shows a banner in that page:


## 10.2. Demonstrate ability to customize customer functionality

### Describe how to add or modify customer attributes

### Describe how to extend the customer entity
### Describe how to customize the customer address
### Describe customer groups and their role in different business processes.
### Describe Magento functionality related to VAT
