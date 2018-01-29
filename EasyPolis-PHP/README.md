# EasyPolis-PHP
By Francois (aka Yoyae) Gineste
https://github.com/Yoyae/EasyPolis-PHP

Tips appreciated: PNAs38vz4b3jEsjbr8tKygtK4JmHwYDA8X

A simple class for making calls to Polis's RPC API using PHP.

## Getting Started:
1. Include easypolis.php into your PHP script:

	`require_once('easypolis.php');`
2. Initialize Polis connection/object:

	`$polis = new \elbereth\EasyPolis('username','password');`

	Optionally, you can specify a host, port. Default is HTTP on localhost port 21426.

	`$polis = new \elbereth\EasyPolis('username','password','localhost','21426');`

	If you wish to make an SSL connection you can set an optional CA certificate or leave blank
	`$polis->setSSL('/full/path/to/mycertificate.cert');`

3. Make calls to polisd as methods for your object. Examples:

	`$polis->getinfo();`
	`$polis->getrawtransaction('c780a21541f163d22f53661f592399fb658d12dc55ef9a7d3e937c4c9705f01a',1);`
	`$polis->getblock('0000000000000124e15bb02d9fa8b5a0cd3e642b148f76aa0c386710d0112cf0');`
	`$polis->mnbudget('show');`

## Additional Info:
* When a call fails for any reason, it will return false and put the error message in $polis->error

* The HTTP status code can be found in $polis->status and will either be a valid HTTP status code or will be 0 if cURL was unable to connect.

* The full response (not usually needed) is stored in $polis->response while the raw JSON is stored in $polis->raw_response

## Contribution Info

This is forked from EasyDash-PHP by Alexandre (aka elbereth) Devilliers (https://github.com/elbereth/EasyDash-PHP ).
Original code is licenced under MIT.
