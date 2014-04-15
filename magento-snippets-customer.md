magento-snippets
================

#Customer

### snippets

#### Check if customer is logged in
```php
<?php $logged_in = Mage::getSingleton('customer/session')->isLoggedIn(); // (boolean) ?>
```

#### Get current customer logged
```php
<?php Mage::getSingleton('customer/session')->getCustomer(); ?>
```

#### Get current logged in admin
```php
<?php Mage::getSingleton('admin/session')->getuser(); ?>
```

#### Get random customer
```php
<?php
/* @var $collection Mage_Customer_Model_Resource_Customer_Collection */
$collection = Mage::getModel('customer/customer')->getCollection();
$collection->getSelect()->order('RAND()')->load();

foreach ($collection as $customer)
{
    /** @var Mage_Customer_Model_Customer $customer */

    ###
}
?>
```

#### Login as customer / user in Magento
```php
<?php
/** @var $customer Mage_Customer_Model_Customer */
$customer = Mage::getModel('customer/customer');

// get the customer (by Mail)
$customer->loadByEmail('customer@example.org');

/** @var $session Mage_Customer_Model_Session */
$session = Mage::getModel('customer/session');
$session->loginById($customer->getId());
?>
```