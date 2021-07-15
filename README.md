# [WIP] PSR Clock

## Work in Progress!

This repository holds the interface for [PSR-20](psr-url).

Note that this is not a clock of its own. It is merely an interface that
describes a clock. See the specification for more details.

**CAVEAT:** This is currently **Work in Progress**! 

**Do not (I repeat: Do NOT) rely on this interface being stable!**

**Using this as long as the PSR is not officially released happens at your own risk!**

## Installation

```bash
# Remember: This PSR is not yet proposed and 
# might change at any time 
# without prior notice
composer require psr/clock
```

## Usage

If you need a clock, you can use the interface like this:

```php
<?php

/*
 * Remember: This PSR is not yet proposed and 
 * might change at any time 
 * without prior notice
 */
use Psr\Clock\ClockInterface;

class Foo
{
    private $clock;

    public function __construct(ClockInterface $clock)
    {
        $this->clock = $clock;
    }

    public function doSomething()
    {
        /** @var DateTimeImmutable $currentDateAndTime */
        $currentDateAndTime = $this->clock()->now();
        // do something useful with that information
    }
}
```

You can then pick one of the [implementations](implementation-url) of the interface to get a clock.

If you want to implement the interface, you can require this package and
implement `Psr\Clock\ClockInterface` in your code. Please read the
[specification text](specification-url)
for details.

[psr-url]: https://www.php-fig.org/psr/psr-20
[package-url]: https://packagist.org/packages/psr/clock
[implementation-url]: https://packagist.org/providers/psr/clock-implementation
[specification-url]: https://github.com/php-fig/fig-standards/blob/master/proposed/clock.md