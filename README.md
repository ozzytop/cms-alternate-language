# Magento 2 CMS Alternate Language

This module allows search-engines to read the content of this page with different alternates depending on
the language of the store view.

In a technical way, it's adding a `<link rel="alternate">` with the proper information for each store view that
is enabled in the CMS page  


## How to install

### 1. via composer

Edit `composer.json`

```
{
    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/ozzytop/cms-alternate-language"
        }
    ],
    "require": {
        "https://github.com/ozzytop/cms-alternate-language": "master"
    }
}
```

```
composer install
php bin/magento setup:upgrade
php bin/magento setup:static-content:deploy
```

### 2. Copy and paste

Download latest version from GitHub

Paste into `app/code/Ozzytop/CMS` directory

```
php bin/magento setup:upgrade
php bin/magento setup:static-content:deploy
```

### 3. Update Origin URL

In the Admin Dashboard go to `Content -> Pages`

Then Select the page that you want to enable this feature. Inside the edit page, go to `Page in Websites` section and
select those store views that you want to show the alternate link.

## How does it work?

The full implementation of CMS Alternate Language is outside the scope of this README, but this is what this module does:

1. Gets the current page Id 
2. Gets all the store's view and check for the base_url and language configuration
3. Builds the `<link rel="alternate">` with the proper information inside the `<header>` tag.

