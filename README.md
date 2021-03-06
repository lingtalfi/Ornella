Ornella
=========================
2015-10-21 -> 2021-03-05






Ornella is a notation for replacing {tags} with a customized value.
It's useful in a few cases where the caller doesn't have access to a programming language, 
and yet you want her to be able to use advanced string functions like strToUpper (converts all to uppercase).  



Ornella is part of the [universe framework](https://github.com/karayabin/universe-snapshot).


Install
==========
Using the [planet installer](https://github.com/lingtalfi/Light_PlanetInstaller) via [light-cli](https://github.com/lingtalfi/Light_Cli)
```bash
lt install Ling.Ornella
```

Using the [uni](https://github.com/lingtalfi/universe-naive-importer) command.
```bash
uni import Ling/Ornella
```



- [ornella tag notation documentation](https://github.com/lingtalfi/ornella/blob/master/ornella-tag-notation.md) 
- [ornella tag implementation in php](https://github.com/lingtalfi/ornella/blob/master/OrnellaTagNotationUtil.php)
 
 
 
 
How to use the php implementation provided in this planet 
-------------------------------------- 


Copy paste the following code and test it in a browser.<br>
The **a** function and the bigbang.php script come from 
the [portable autoloader technique](https://github.com/lingtalfi/TheScientist/blob/master/convention.portableAutoloader.eng.md).


```php
<?php


use Ling\Ornella\OrnellaTagNotationUtil;

require_once "bigbang.php";



$strings=[
    '{fileName:upper}.{ext}.{fileName:safe_-:upper:cut_-_1;3-4_+\_+}',
    '{fileName:upper}.{ext}.{fileName:safe_-:upper:cut_-_1;3-4_+\:+}',
    '{fileName:upper}.{ext}.{fileName:safe_-:upper:cut_-_1;3-4_-}',
    '{fileName:upper}.{ext}.{fileName:safe_-:upper:cut_-_1;3-4}',
    '{fileName:upper}.{ext}.{fileName:safe_-:upper:cut_-_1;3}',
    '{fileName:upper}.{ext}.{fileName:safe_-:upper:cut_-_2+}',
    '{fileName:upper}.{ext}.{fileName:safe_-:upper}',
    '{fileName:upper}.{ext}.{fileName:substr_0}',
    '{fileName:upper}.{ext}.{fileName:substr_1}',
    '{fileName:upper}.{ext}.{fileName:substr_-3}',
    '{fileName:upper}.{ext}.{fileName:substr_2_6}',
    '{fileName:upper}.{ext}.{fileName:substr_2_-2}',
];




$tagValues = [
    'fileName' => 'wood-tiger-from-the-hood',
    'ext' => 'txt',
];

$string = end($strings);

$o = OrnellaTagNotationUtil::create();
if (false !== ($str = $o->parse($string, $tagValues))) {
    a($str);
}
else {
    echo '<hr>';
    a($o->getErrors());
}

```


History Log
===============

- 1.0.4 -- 2021-05-31

    - Removing trailing plus in lpi-deps file (to work with Light_PlanetInstaller:2.0.0 api

- 1.0.3 -- 2021-03-05

    - update README.md, add install alternative

- 1.0.2 -- 2020-12-08

    - Fix lpi-deps not using natsort.

- 1.0.1 -- 2020-12-04

    - Add lpi-deps.byml file

- 1.0.0 -- 2015-10-21

    - initial commit




