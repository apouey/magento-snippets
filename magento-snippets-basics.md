magento-snippets
================

#Basics

## Magento Codepools

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

## Magento module structure

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