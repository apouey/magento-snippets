magento-snippets
================

#Basics

## High-level Magento architecture 

### Magento Codepools

Magento has three different codepools:

* Community (app/code/community)
* Core (app/code/code)
* Local (app/code/local)

Extract of app/Mage.php

```php
/**
* Set include path
*/
$paths[] = BP . DS . 'app' . DS . 'code' . DS . 'local';
$paths[] = BP . DS . 'app' . DS . 'code' . DS . 'community';
$paths[] = BP . DS . 'app' . DS . 'code' . DS . 'core';
$paths[] = BP . DS . 'lib';

$appPath = implode(PS, $paths);
set_include_path($appPath . PS . Mage::registry('original_include_path'));
include_once "Mage/Core/functions.php";
include_once "Varien/Autoload.php";
```

### Magento module structure

```php
Namespace
	|-- Modulename
		|-- Block
		|-- controllers
		|-- etc
		|-- Helper
		|-- Model
		|-- sql
```

### Magento templates location

```php
app
|-- design
	|-- frontend
		|-- package_name
			|-- theme_name
				|-- template
					|-- *.phtml
```

### Magento Layout files location

```php
app
|-- design
	|-- frontend
		|-- package_name
			|-- theme_name
				|-- layout
					|-- *.xml
```

### Magento Locale files location

```php
app
|-- design
	|-- frontend
		|-- package_name
			|-- theme_name
				|-- locale
					|-- *.csv
```

### Magento skin files location

```php
skin
|-- frontend
	|-- package_name
		|-- theme_name
			|-- js
			|-- css
			|-- images
```

### Magento design areas (adminhtml and frontend)

```php
app
|-- design
	|-- adminhtml
	|-- frontend
	|-- install
```

```php
app
|-- design
	|-- area_name
		|-- package_name
```

### Magento class naming conventions

 * Based on the Zend Framework class naming convention
 * Depending on their location in the file system
 * Varien_Autoload is used for automatic upload

### Resolving module conflicts. 

@todo

## Magento configuration

### Magento configuration information

@todo

### Class group configuration 

@todo

### Class overrides in Magento

@todo

### Observers

@todo

### Events

@todo

### Cron job 

@todo

## Internationalization 

### Internationalization of a Magento site

@todo

### Magento translate classes and translate files

@todo

### Using subdomains and subdirectories in internationalization

@todo
