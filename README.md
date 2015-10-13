Yii2 Captcha
================
Распознавание капч.

Особенности
------------
* Подходит для всех сервисов по распознаванию капч работающие по общим стандартам
* Лёгкость настроки
* Распозвание как по пути до файла, так и по ссылки

Установка
------------
Предпочтительный способ установить это расширение через [composer](http://getcomposer.org/download/).

Либо запустить

```
php composer.phar require --prefer-dist jumper423/yii2-captcha "*"
```

или добавить

```
"jumper423/yii2-captchar": "*"
```

в файл `composer.json`.

Configuration:

```php
'components' => [
    'captcha' => [
        'class' => 'jumper423\Captcha',
        'pathTmp' => '@common/captcha',
        'apiKey' => '42eab4119020dbc729f657fef270r546',
    ],
],
```

Использование
------------
Простой пример использования:

```php
if (\Yii::$app->captcha->run('path/to/captcha.png')) {
    $captcha = \Yii::$app->captcha->result()
} else {
    throw new Exception(\Yii::$app->captcha->error());
}
```