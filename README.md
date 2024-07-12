<p align="center">
  <img src="https://github.com/esrayildiizz/Example/assets/106755194/e0197438-b265-449a-a90b-cf4f526a0e01" alt="PAYGATE Image"/>
</p>

<p align="center">
<strong>PAYGATE</strong>
</p>

<p align="center">
PayGate ile tüm online ödemelerinizi tek merkezden yönetin 
</p>
<p align="center">
katma değerli servislerimiz ile ödeme giderlerinizi azaltın, cironuzu artırın ve işletmenizi büyütün.
</p>

## PAYGATE
[![Craftgate Dotnet CI](https://img.shields.io/badge/Craftgate%20Dotnet%20CI-passing-brightgreen)]()
[![nuget](https://img.shields.io/badge/nuget-v1.0.61-blue)]()
[![Gitpod ready-to-code](https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod)]()


## Requirements
- .NET Framework 4.6+
- .NET Core 1.1+
- .NET Core 2.0+

## Installation
`Install-Package  ...... `



## Usage
PayGate API'sine erişmek için öncelikle API kimlik bilgilerini (örneğin bir API anahtarı ve gizli anahtar) edinmeniz gerekir. Zaten bir Craftgate hesabınız yoksa https://paygate.io/ adresinden kaydolabilirsiniz.

API kimlik bilgilerinizi aldıktan sonra, PayGate kimlik bilgilerinizle bir örnek oluşturarak PayGate'i kullanmaya başlayabilirsiniz.


`$craftgate = new \PayGate\PayGate(array(
    'apiKey' => '<YOUR API KEY>',
    'secretKey' => '<YOUR SECRET KEY>',
));`


Varsayılan olarak PayGate istemcisi üretim API sunucularına bağlanır https://api.paygate.io. Test amaçlı olarak lütfen https://sandbox-api.paygate.io. kullanarak deneme alanı URL'sini kullanın.


`$paygate = new \PayGate\PayGate(array(
    'apiKey' => '<YOUR API KEY>',
    'secretKey' => '<YOUR SECRET KEY>',
    'baseUrl' => 'https://sandbox-api.paygate.io',
));`


## Examples


### Running the Examples


### Credit Card Payment Use Case

```php
$craftgate = new \Craftgate\Craftgate(array(
    'apiKey' => '<YOUR API KEY>',
    'secretKey' => '<YOUR SECRET KEY>',
    'baseUrl' => 'https://sandbox-api.craftgate.io',
));

$request = array(
    'price' => 100,
    'paidPrice' => 100,
    'walletPrice' => 0,
    'installment' => 1,
    'currency' => \Craftgate\Model\Currency::TL,
    'paymentGroup' => \Craftgate\Model\PaymentGroup::LISTING_OR_SUBSCRIPTION,
    'conversationId' => '456d1297-908e-4bd6-a13b-4be31a6e47d5',
    'card' => array(
        'cardHolderName' => 'Haluk Demir',
        'cardNumber' => '5258640000000001',
        'expireYear' => '2044',
        'expireMonth' => '07',
        'cvc' => '000'
    ),
    'items' => array(
        array(
            'externalId' => \Craftgate\Util\Guid::generate(),
            'name' => 'Item 1',
            'price' => 30
        ),
        array(
            'externalId' => \Craftgate\Util\Guid::generate(),
            'name' => 'Item 2',
            'price' => 50
        ),
        array(
            'externalId' => \Craftgate\Util\Guid::generate(),
            'name' => 'Item 3',
            'price' => 20
        )
    )
);

$response = $craftgate->payment()->createPayment($request);

var_dump($response);
```



### Contributions
For all contributions to this client please see the contribution guide here.

## License

*MIT*
