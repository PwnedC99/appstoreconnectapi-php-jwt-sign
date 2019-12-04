# appstoreconnectapi-php-jwt-sign
AppstoreconnectApi Sign Class For PHP

```PHP
<?php

require './ECSign.php';

$key = <<<EOF
-----BEGIN PRIVATE KEY-----
YOUR p8 KEY File Content
-----END PRIVATE KEY-----
EOF;

$header = [
    'alg' => 'ES256',
    'kid' => 'Your Kid',
    'typ' => 'JWT',
];

$payload = [
    'iss' => 'YOUR Issuer ID',
    'exp' => time() + 600,
    'aud' => 'appstoreconnect-v1'
];

$token =  ECSign::sign($payload, $header, $key);
echo $token;

//Just Run Test
//curl -v -H 'Authorization: Bearer <YOUR TOKEN>' "https://api.appstoreconnect.apple.com/v1/apps"
```