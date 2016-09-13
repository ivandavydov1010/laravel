# Parse, build and manipulate URL's

[![Latest Version on Packagist](https://img.shields.io/packagist/v/spatie/url.svg?style=flat-square)](https://packagist.org/packages/spatie/url)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)
[![Build Status](https://img.shields.io/travis/spatie/url/master.svg?style=flat-square)](https://travis-ci.org/spatie/url)
[![SensioLabsInsight](https://img.shields.io/sensiolabs/i/xxxxxxxxx.svg?style=flat-square)](https://insight.sensiolabs.com/projects/xxxxxxxxx)
[![Quality Score](https://img.shields.io/scrutinizer/g/spatie/url.svg?style=flat-square)](https://scrutinizer-ci.com/g/spatie/url)
[![Total Downloads](https://img.shields.io/packagist/dt/spatie/url.svg?style=flat-square)](https://packagist.org/packages/spatie/url)

A simple package to deal with URL's in your applications.

Retrieve parts of the URL:

```php
$url = Url::fromString('https://spatie.be/opensource');

echo $url->getScheme(); // 'https'
echo $url->getHost(); // 'spatie.be'
echo $url->getPath(); // '/opensource'
```

Transform any part of the URL (the `Url` class is immutable):

```php
$url = Url::fromString('https://spatie.be/opensource');

echo $url->withHost('github.com')->withPath('spatie');
// 'https://github.com/spatie'
```

Retrieve and transform query parameters:

```php
$url = Url::fromString('https://spatie.be/opensource?utm_source=github&utm_campaign=pacakges');

echo $url->getQuery(); // 'utm_source=github&utm_campaign=pacakges'
echo $url->getQueryParameter('utm_source'); // 'github'
echo $url->withoutQueryParameter('utm_campaign'); // 'https://spatie.be/opensource?utm_source=github'
```

Retrieve path segments:

```php
$url = Url::fromString('https://spatie.be/opensource/laravel');

echo $url->getSegment(1); // 'opensource'
echo $url->getSegment(2); // 'laravel'
```

Implements PSR-7's `UriInterface` interface:

```php
class Url implements UriInterface { /* ... */ }
```

The [`league/uri`](https://github.com/thephpleague/uri) is a more powerful package than this one. The main reason this package exists, is because the the alternative requires non-standard php extensions. If you're dealing with special character encodings or need bulletproof validation, you're definitely better off using `league/uri`.

Spatie is a webdesign agency based in Antwerp, Belgium. You'll find an overview of all our open source projects [on our website](https://spatie.be/opensource).

## Postcardware

You're free to use this package (it's [MIT-licensed](LICENSE.md)), but if it makes it to your production environment you are required to send us a postcard from your hometown, mentioning which of our package(s) you are using.

Our address is: Spatie, Samberstraat 69D, 2060 Antwerp, Belgium.

The best postcards will get published on the open source page on our website.

## Installation

You can install the package via composer:

``` bash
composer require spatie/url
```

## Usage

``` php
$skeleton = new Spatie\Skeleton();
echo $skeleton->echoPhrase('Hello, Spatie!');
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Testing

``` bash
$ composer test
```

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Security

If you discover any security related issues, please email freek@spatie.be instead of using the issue tracker.

## Credits

- [Sebastian De Deyne](https://github.com/sebastiandedeyne)
- [All Contributors](../../contributors)

## About Spatie
Spatie is a webdesign agency based in Antwerp, Belgium. You'll find an overview of all our open source projects [on our website](https://spatie.be/opensource).

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
