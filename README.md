# uptime-parser

[![Build Status](https://travis-ci.org/vitorbari/uptime-parser.svg?branch=master)](https://travis-ci.org/vitorbari/uptime-parser)
[![StyleCI](https://styleci.io/repos/64677269/shield)](https://styleci.io/repos/64677269)
[![Coverage Status](https://coveralls.io/repos/github/vitorbari/uptime-parser/badge.svg?branch=master)](https://coveralls.io/github/vitorbari/uptime-parser?branch=master)

A PHP package for parsing uptime command output

## Installation

Via Composer.

```
composer require vitorbari/uptime-parser
```

## Usage


```php
use VitorBari\UptimeParser\Parser;

$uptime_output = 'SNMP OK - Timeticks: (197181577) 22 days, 19:43:35.77';

$uptime = Parser::uptime($uptime_output);

echo $uptime->days; // 22
echo $uptime->hours; // 547
echo $uptime->minutes; // 32863
echo $uptime->seconds; // 1971815
echo $uptime->toTimeString(); // '22 day(s), 19 hour(s), 43 minute(s) and 35 second(s)'
echo $uptime; // '22 day(s), 19 hour(s), 43 minute(s) and 35 second(s)'

```


## Supported Formats


```
SNMP OK - Timeticks: (197181577) 22 days, 19:43:35.77
SNMP OK - Timeticks, (12490039) 1 day, 10,41,40.39
SNMP OK - Timeticks, (6261427) 17,23,34.27
System Uptime - 44 day(s) 23 hour(s) 14 minute(s)
System Uptime - up 57 days, 12 Hours, 41 Minutes
System Uptime - 10 minute(s)
Sistema ativo a 32 Dia(s), 10 Hora(s) e 38 Minutos(s)
```

Different formats can be easily added.