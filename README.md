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
[![Paygate Dotnet CI](https://img.shields.io/badge/Paygate%20Dotnet%20CI-passing-brightgreen)]()
[![nuget](https://img.shields.io/badge/nuget-v1.0.61-blue)]()


## Gereksinimler
- .NET Standart 2.0
- .NET Core 8 (Tests ve Web projeleri için)

## Kurulum
`Install-Package  ...... `



## Kullanım
PayGate API'sine erişmek için öncelikle API kimlik bilgilerini (örneğin bir API anahtarı ve gizli anahtar) edinmeniz gerekir. 

API kimlik bilgilerinizi aldıktan sonra, PayGate kimlik bilgilerinizle bir örnek oluşturarak PayGate'i kullanmaya başlayabilirsiniz.

## Örnekler

### Kredi Kartı Ödeme Kullanım Örneği

```php
$request = array(
    'amount' => 100,
    'paidamount' => 100,
    'walletamount' => 0,
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
);

$response = $createPaymentAsync($request);

var_dump($response);
```



### Katkılar
For all contributions to this client please see the contribution guide here.

## Lisans

*MIT*
