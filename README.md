# Simple PHP class for BitBayPay REST API

## Usage

The BitBayPayAPI constructor receive public and private key using to authentication. 
```php
<?php

require_once('BitbayPayApi.class.php');

$api = new bitbaypayAPI('1c990eb1-fab5-4890-98fd-3ec4bf185254', 'dd607870-a151-4ffa-a57b-a0c4b70dded3');

$api->getPaymentDetails('7bb298f2-1294-11e9-ab14-d663bd873d93');
```
## Available endpoints

### Start payment
```php
$params = array(
  "destinationCurrency" => "PLN",
  "keepSourceCurrency" => false,
  "orderId" => "e5rh45uq34udomAEADFGqa3ySDF3sd",
  "price" => 199,
  "sourceCurrency" => "BTC"
);

return $api->startPayment($params);
```

### Get available currency pairs
```php
return $api->getCurrencyPairs();
```

### Get payment details
```php
return $api->getPaymentDetails('7bb298f2-1294-11e9-ab14-d663bd873d93');
```

### Funds withdrawal
```php
$params = array(
  "destinationAddress" => "1HB5XMLmzFVj8ALj6mfBsbifRoD4miY36v",
  "destinationCurrency" => "BTC",
  "orderId" => "e5rh45uq34udomAEADFGqa3ySasdzxDF3sd",
  "sourcePrice" => 0.523
);

return $api->withdrawalFunds($params);
```
