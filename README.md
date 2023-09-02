# MAD Logo's by MAD Tech Services
This component is a multipurpose logo component that can be used in any project. It allows you to easily add custom branding to Larvel applications easily. It requires Laravel Nova and is controlled via the Nova dashboard.

## Features
+ Custom Logo's for ...
  + Laravel Nova
  + Laravel Jetstream
  + Laravel Fortify
  + Laravel Breeze
  + Laravel Telescope
  + More to come...
+ Built in ability to add logo's for different themes such as default, dark, and light.
+ Built in ability to add custom logo links.
+ Built in ability to add custom logo classes to modify size, color, etc.
+ Allows you to upload the following...
  + Site header logo - Main Branding
  + Site login logo
  + Site footer logo
  + Site favicon
  + Dashboard menu logo
+ Allows you to add different links for each area, so your nova logo may link to https://yoursite.com/nova and your jetstream logo could be https://yoursite.com/dashboard
+ Allows you to work with different file types including the following...
  + PNG
  + JPG
  + SVG
  + ICO
  + More to come...
+ Allows you to use different file stores such as local, s3, custom, web url etc.
+ Quick change between logo's from the MAD Logos settings page.

## Planned Features coming soon...
A few other features we are working on include the following...
+ Add text based logo's using google fonts and easy to use wysiwyg editor to customise your text based logo.
+ Ability to mix an icon or logo and text based logo together.
+ Ability to use AI to make a logo from scratch.
+ Branding manager and builder.
+ More to come...

## Requirements

- `php: ^7.3|^8.1`
- `laravel/nova: ^4.0`
- `stepenenko3/nova-settings`

## Installation

Install the package in to a Laravel app that uses [Nova](https://nova.laravel.com) via composer:

```bash
composer require madtechservices/madlogos
```

## Usage

### Configuration Options

To configure the logo options, make the following modifications...

### For Laravel Nova

Modify the `config/nova.php`

```php
// config/nova.php
return [
    'brand' => [
        'logo_src' => settings('mylogos', 'logo_src'),
        'logo_src_dark' => settings('mylogos', 'logo_src_dark'),
        'logo_src_light' => settings('mylogos', 'logo_src_light'),
        'icon_src' => settings('mylogos', 'icon_src'),
        'icon_src_dark' => settings('mylogos', 'icon_src_dark'),
        'icon_src_light' => settings('mylogos', 'icon_src_light'),
        'logo_href' => settings('mylogos', 'logo_link'),
        'nova_href' => settings('mylogos', 'nova_link'),
        'nova_favicon' => settings('mylogos', 'nova_favicon'),
        'logo_class' => settings('mylogos', 'logo_class'),
        'logo_alt' => settings('mylogos', 'logo_text'),
    ]
]
```
### For Laravel Jetstream
STILL NEED TO WORK THIS OUT

#### Jetstream Change 1
Modify the `resources/views/components/application-logo.blade.php`

```php
// resources/views/components/application-logo.blade.php
<img src="{{ settings('mylogos', 'jet_logo_src') }}" alt="{{ settings('mylogos', 'jet_logo_text') }}" class="{{ settings('mylogos', 'jet_logo_class') }}" />
```

#### Jetstream Change 2
Modify the `resources/views/components/application-mark.blade.php`

```php
// resources/views/components/application-mark.blade.php
<img src="{{ settings('mylogos', 'jetmark_logo_src') }}" alt="{{ settings('mylogos', 'jetmark_logo_text') }}" class="{{ settings('mylogos', 'jetmark_logo_class') }}" />
```

#### Jetstream Change 3
Modify the `resources/views/components/authentication-card-logo.blade.php`

```php
// resources/views/components/authentication-card-logo.blade.php
<img src="{{ settings('mylogos', 'jetauth_logo_src') }}" alt="{{ settings('mylogos', 'jetauth_logo_text') }}" class="{{ settings('mylogos', 'jetauth_logo_class') }}" />
```

### Changes for Laravel Fortify

### Changes for Laravel Telescope

### Changes for Laravel Breeze

### Changes for Laravel Spark


### Deprecated Configuration Options

Please note that as of 2.0.0 the following configuration options are now deprecated, and will be removed in a future release, please see the new configuration options above.

```
'logo_url'
'logo_link'
```

### Known Issues
- Internal links will result in a full page load rather than following an Inertia Link
- Due to the way Nova loads package scripts, this will not work for the login page, I recommend using your own login (or breeze or similar) and overriding the login links:

```php
    // config/nova.php
    'routes' => [
        'login' => '/login',
        'logout' => '/logout',
        'register' => '/register',
        'forgot_password' => '/forgot_password',
        'reset_password' => '/reset_password'
    ],
```


## License

Nova Logo Url is open-sourced software licensed under the [MIT license](LICENSE.md).
