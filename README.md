# magento2-patches
Patches that relate to specific PR's to be used with https://github.com/cweagans/composer-patches

## Usage

The patches have been created to be used for composer M2 projects.

1. In project root folder, run these commands:

```bash
composer config repositories.ripen-patches vcs https://github.com/ripenecommerce/magento2-patches.git
composer require ripenecommerce/magento2-patches=dev-master
```

2. The project `composer.json` should also already have an "extra" key defined. Add a new sub-key there called 
   "patches" along with the specific patch definitions to apply (see last section below). Then the next time you do
   `composer update`, the modules that have patches defined will be re-installed and patches applied. 

## Patch Creation

TODO: Complete instructions.

Patches have file-target paths that are relative to composer packages.

## Definitions for Patches

```json
{
    "extra": {
        "patches": {
            "magento/module-catalog": {
                "Fix: https://github.com/magento/magento2/issues/5438":
                "https://raw.githubusercontent.com/ripenecommerce/magento2-patches/master/Patch-Magento_Catalog-M2.1.0-image-attribute-backend-model-hardcoded-attribute-code-removal.patch",

                "Fix: https://github.com/magento/magento2/issues/6076":
                "https://raw.githubusercontent.com/ripenecommerce/magento2-patches/master/Patch-Magento_Catalog-0001-MAGETWO-54223-CMS-Widgets-Catalog-Category-Link-widg.patch",

                "Fix: https://github.com/magento/magento2/issues/5931 and https://github.com/magento/magento2/issues/5612":
                "https://raw.githubusercontent.com/ripenecommerce/magento2-patches/master/Patch-Magento_Catalog-M2.1.5-MAGETWO-56410-MAGETWO-56411-github-issues-5931-5612.patch"
            },
            "magento/module-customer": {
                "Fix: https://github.com/magento/magento2/issues/10838":
                "https://raw.githubusercontent.com/ripenecommerce/magento2-patches/Patch-Magento-Customer-grid-indexer-add-missing-function.patch"
            },
            "magento/module-payment": {
                "Fix: https://github.com/magento/magento2/pull/9365":
                "https://raw.githubusercontent.com/ripenecommerce/magento2-patches/master/Patch-Magento_Payment-M2.1.3-MAGETWO-60351-optimize-payment-methods-checkout.patch"
            },
            "magento/module-ui": {
                "Fix: https://github.com/magento/magento2/issues/5438":
                "https://raw.githubusercontent.com/ripenecommerce/magento2-patches/master/Patch-Magento_Ui-M2.1.0-allow-backend-to-know-the-origin-input-of-the-upload-request.patch"
            },
            "magento/module-vault": {
                "Fix: https://github.com/magento/magento2/pull/9365":
                "https://raw.githubusercontent.com/ripenecommerce/magento2-patches/master/Patch-Magento_Vault-M2.1.3-MAGETWO-60351-optimize-payment-methods-checkout.patch"
            },
            "magento/magento2-base": {
                "Fix: https://github.com/magento/magento2/issues/4232":
                "https://raw.githubusercontent.com/ripenecommerce/magento2-patches/master/Patch-Magento_Base-0001-MAGETWO-52850-GitHub-UTF-8-special-character-issue-i.patch"
            }
        }
    }
}
```
