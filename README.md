-------
# «Твои платежи», модуль для CMS Wordpress WooCommerce

![](https://repository-images.githubusercontent.com/638835276/ff494b04-d65b-4843-8759-e85c689a7e80)

[НКО «Твои Платежи»](https://YPMN.ru/ "Платёжная система для сайтов, платформ и приложений") - платёжная система для сайтов, платформ, игр и приложений.


{Корень сайта}/wp-content/plugins/woocommerce/classes/gateways/
( Обратите внимание, что модуль уже содержит ссылку для IPN-запроса )

##Установка
-------------
1. Скопируйте папку payu в папку своего сайта на Wordpress: 
 ```
  {Корень сайта}/wp-content/plugins/woocommerce/includes/gateways
 ```
2. Найдите класс WC_Payment_Gateways. По умолчанию он находится по следующему адресу: 
 ```
 {Корень сайта}/wordpress/wp-content/plugins/woocommerce/includes/class-wc-payment-gateways.php
 ```
3. Откройте файл, в котором реализован класс WC_Payment_Gateways.
4. Добавьте туда систему PayU. Для этого необходимо добавить WC_Gateway_PayU в массив load_gateways. Впишите следующий фрагмент кода:
  ```
 $load_gateways = array(
			'WC_Gateway_BACS',
			'WC_Gateway_Cheque',
			'WC_Gateway_COD',
			'WC_Gateway_Paypal',
			'WC_Gateway_PayU',
		);
 ```
5. Зайдите в административную консоль своего сайта на Wordpress. 
6. Через главное меню перейдите Woocommerce > Настройки.
7. Зайдите на вкладку Платежи (Payment Gateways). 
8. Выберите PayU в списке.
9. Настройте модуль согласно подсказкам. Не забудьте установить тестовый режим для проверки модуля.
10. Обратите внимание на ссылку для IPN на странице с настройками платёжного модуля. Эта ссылку нужно указать на странице https://secure.ypmn.ru/cpanel/ipn_settings.php.
