WordPress Core Autoloader for Composer
=====================================

> DO NOT USE YET. THIS IS STILL A WORK IN PROGRESS.

Usage
-----

In your project's `composer.json`, add the following lines:

```json
{
    "require": {
        "schlessera/composer-wp-autoload": "^1"
    },
    "scripts": {
        "post-install-cmd": [
            "WordPress\\ComposerAutoload\\Generator::onPostInstallCmd"
        ],
        "post-update-cmd": [
            "WordPress\\ComposerAutoload\\Generator::onPostInstallCmd"
        ],
        "post-autoload-dump": [
            "WordPress\\ComposerAutoload\\Generator::onPostInstallCmd"
        ]
    },
    "extra": {
        "wordpress-autoloader": {
            "source-prefix": "'src/'",
            "destination-prefix": "ABSPATH"
        },
    }
}
```

After the next update/install, you will have a `vendor/autoload_wordpress.php` file, that you can simply include and use to autoload classes within WordPress Core.
