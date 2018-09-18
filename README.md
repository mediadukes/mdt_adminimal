# Custom Drupal 8 subtheme for the Adminimal theme

This subtheme is an opiniated subtheme of the 
[adminimal_theme](https://www.drupal.org/project/adminimal_theme). We consider 
it as a startingpoint on which can be built further if needed.

## Usage

Just install as any other drupal module using `composer require`.

```
composer require mediadukes/mdt_adminimal:^1.x
```

## Requirements

If it's not already present in your repositories array you'll need to define 
inside your root `composer.json` where mediadukes packages can be found.

```
"repositories": [
  {
    "type": "composer",
    "url": "https://packages.mediadukes.be"
  }
]
```

We also defined a custom type in this theme's `composer.json` so we can install 
it directly inside the `themes/custom` directory for easy future modifications. 
For that to work it requires the 
[oomphinc/composer-installers-extender](https://packagist.org/packages/oomphinc/composer-installers-extender) 
composer plugin and you need to add following snippet to your root `composer.json`:

```
"extra": {
  "installer-types": [
    "drupal-custom-theme"
  ],
  "installer-paths": {
    "web/themes/contrib/{$name}": [
      "type:drupal-theme",
      "type:drupal-custom-theme"
    ]
  }
}
```

Or you can use the 
[mediadukes drupal-project template](https://github.com/mediadukes/drupal-project) 
where all of this is already included in it's `composer.json`.
