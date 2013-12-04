YATSATRAP!
===

Yet Another Twitter SAss bootsTRAP
---
*(yeah, i know...)*

This is a stripped down fork of [thomas-mcdonald/bootstrap-sass](https://github.com/thomas-mcdonald/bootstrap-sass), without all the rails/compass install/build/integration superbloated toolkit. Just plain SASS and JS.


Version
---

**3.0.2**

[Semver](http://semver.org) tags map to actual [Twitter Bootstrap](http://getbootstrap.com) versions. Custom suffixes may appear for maintenance.


Installation and usage
---

You can clone/download the repo or use [Bower](http://bower.io)

`bower install yatsatrap`


**The CSS**

Just simple as:

`@import path/to/yatsatrap/sass/bootstrap`


**The Javascript**

The js sources are provided uncompressed, both in the single file `js/bootstrap-full.js` and divided by component.
You can delve into using only some components, but you'll have to deal with dependencies by yourself (see the [official docs](http://getbootstrap.com/javascript)).

For reference, here is the order by which the components are loaded in the single file:

*  `bootstrap-transition.js`
*  `bootstrap-alert.js`
*  `bootstrap-button.js`
*  `bootstrap-carousel.js`
*  `bootstrap-collapse.js`
*  `bootstrap-dropdown.js`
*  `bootstrap-modal.js`
*  `bootstrap-tooltip.js`
*  `bootstrap-popover.js`
*  `bootstrap-scrollspy.js`
*  `bootstrap-tab.js`
*  `bootstrap-affix.js`


**ZF2 AssetManager**

Since my whole aim for this package is to use minimal sources with my asset manager of choice, here is a snippet that provides some basic configuration for [RWOverdijk/AssetManager](https://github.com/RWOverdijk/AssetManager)

```php
return [
    'asset_manager' => [
        'resolver_configs' => [
            'collections' => [
                'css/bootstrap.css' [
                    'sass/bootstrap.scss',
                ],
                'js/bootstrap.js' => [
                    'js/bootstrap-transition.js',
                    'js/bootstrap-alert.js',
                    'js/bootstrap-button.js',
                    'js/bootstrap-carousel.js',
                    'js/bootstrap-collapse.js',
                    'js/bootstrap-dropdown.js',
                    'js/bootstrap-modal.js',
                    'js/bootstrap-tooltip.js',
                    'js/bootstrap-popover.js',
                    'js/bootstrap-scrollspy.js',
                    'js/bootstrap-tab.js',
                    'js/bootstrap-affix.js',
                ],
            ],
            'paths' => [
                'path/to/yatsatrap',
            ],
        ],
        'filters' => [
            'css/bootstrap.css' => [
                [ 'filter' => 'ScssFilter' ],
            ],
            'css/bootstrap-responsive.css' => [
                [ 'filter' => 'ScssFilter' ],
            ],
            'js/bootstrap.js' => [
                [ 'filter' => 'UglifyJs2' ]
            ],
        ],
    ],
];
```

Your mileage may of course vary.
