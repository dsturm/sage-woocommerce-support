# Sage Woocommerce Support #

Add Woocommerce blade template and controllers support for Sage 9 based themes.

## Installation ##

Run inside theme directory.

`composer require kimhf/sage-woocommerce-support`

## Requirements ##

PHP 7.1 or above

## Usage ##

Example: To override the template `plugins/woocommerce/templates/single-product.php` create `themes/yoursagetheme/resources/views/single-product.blade.php` or `themes/yoursagetheme/resources/views/woocommerce/single-product.blade.php`

Example: To override the partial `plugins/woocommerce/templates/content-product.php` create `themes/yoursagetheme/resources/views/partials/content-product.blade.php` or `themes/yoursagetheme/resources/views/woocommerce/content-product.blade.php` or `themes/yoursagetheme/resources/views/content-product.blade.php`

## Details ##

The package will look for templates in the paths defined in the Sage config `view.paths`. It will search for both .php and .blade.php files.

Data from controllers and args from woocommerce will always be added to blade templates, even if you mix usage between php and blade templates.

### With default Sage and WooCommerce config: ###

A template from the template hierarchy will loaded from `resources/views/woocommerce` or `resources/views` as entry template. (WC_Template_Loader will only load the empty resources/index.php in this case.)

`wc_get_template()` Will with default config look inside `resources/views/woocommerce` and `resources/views`. $args added by Woocommerce will take priority over controller data if there are any conflicts.

`wc_get_template_part()` Will with default config look inside `resources/views/woocommerce`, `resources/views/partials` and `resources/views`.

`wc_get_template_html()` Is not supported.
