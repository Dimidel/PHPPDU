# PHPPDU [![Build Status](https://travis-ci.org/jackkum/PHPPDU.svg?branch=master)](https://travis-ci.org/jackkum/PHPPDU) [![Code Climate](https://codeclimate.com/github/jackkum/PHPPDU/badges/gpa.svg)](https://codeclimate.com/github/jackkum/PHPPDU)

Creating a PDU string for sending sms

# Usage
----------------------

```php
require_once './jackkum/PHPPDU/Autoloader.php';

\jackkum\PHPPDU\Autoloader::register();

$pdu = new \jackkum\PHPPDU\Submit();

$pdu->setAddress("*********");
$pdu->setData("Message to sent.");

foreach($pdu->getParts() as $part){
	echo get_class($part), PHP_EOL;
	echo (string) $part, PHP_EOL;
}
```
----------------------

```php
$pdu = \jackkum\PHPPDU\PDU::parse($str);

echo $pdu->getAddress()->getPhone(), PHP_EOL;

foreach($pdu->getParts() as $part){
	$header = $part->getHeader();
	echo "unique: ", $header->getPointer(), PHP_EOL;
	echo $header->getCurrent(), " of ", $header->getSegments(), PHP_EOL;
	echo $tmp->getData()->getData(), PHP_EOL;
}

```
----------------------

# TODO
 - Merge parsed messages
