[<img src="https://github-ads.s3.eu-central-1.amazonaws.com/support-ukraine.svg?t=1" />](https://supportukrainenow.org)

# Public telegram channels scrapper

[![Latest Version on Packagist](https://img.shields.io/packagist/v/ymsoft/telegram-channel-scrapper.svg?style=for-the-badge)](https://packagist.org/packages/ymsoft/telegram-channel-scrapper)
[![License](https://img.shields.io/github/license/yarmat/telegram-channel-scrapper?style=for-the-badge)](https://github.com/yarmat/telegram-channel-scrapper/blob/master/LICENSE.md)

[![PHP from Packagist](https://img.shields.io/packagist/php-v/ymsoft/telegram-channel-scrapper?style=flat-square)](https://packagist.org/packages/ymsoft/telegram-channel-scrapper)
[![PHP Composer](https://github.com/yarmat/telegram-channel-scrapper/actions/workflows/php.yml/badge.svg?branch=master)](https://github.com/yarmat/telegram-channel-scrapper/actions/workflows/php.yml)
[![Total Downloads](https://img.shields.io/packagist/dt/ymsoft/telegram-channel-scrapper.svg?style=flat-square)](https://packagist.org/packages/ymsoft/telegram-channel-scrapper)

This package is intended for those who need to efficiently scrape a public telegram channel.
This is done quite easily:
```php
use Ymsoft\TelegramChannelScrapper\TelegramCS;

$scrapper = new TelegramCS('channel_name');

/** @var \Ymsoft\TelegramChannelScrapper\Entity\Channel $channel */
$channel = $scrapper->getChannel();
/** 
 * By default, you will scrap the latest 20 messages.
 * @var \Illuminate\Support\Collection<\Ymsoft\TelegramChannelScrapper\Entity\Message\Message> $messages 
 */
$messages = $scrapper->getMessages();
$messages->count(); // will return 20

// In order to download 20 more messages you need
$scrapper->loadPrevMessages();

$scrapper->getMessages()->count() // will return 40

// You can download old messages endlessly until you download everything.
```

## Installation

You can install the package via composer:

``` bash
composer require ymsoft/telegram-channel-scrapper
```

## Testing

``` bash
composer test
```

## Changelog

Please see [CHANGELOG](https://github.com/yarmat/telegram-channel-scrapper/releases) for more information on what has changed recently.

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.