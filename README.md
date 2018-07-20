Yii2-review
==========
Модуль добавления отзывов для товара.

Установка
---------------------------------
Выполнить команду

```
php composer require mydesign/yii2-review "@dev"
```

Или добавить в composer.json

```
"mydesign/yii2-review": "@dev",
```

И выполнить

```
php composer update
```

Далее, мигрируем базу:

```
php yii migrate --migrationPath=vendor/mydesign/yii2-review/src/migrations
```

Подключение и настройка
---------------------------------
В конфигурационный файл приложения добавить модуль review

```php
    'modules' => [
        'review' => [
            'class' => 'mydesign\review\Module',
        ],
        //...
    ]
```

Виджеты
---------------------------------
За вывод формы заказа отвечает виджет mydesign\review\widgets\ReviewForm

```php
<?php
use mydesign\review\widgets\ReviewList;
use mydesign\review\widgets\ReviewForm;
?>

Выведет список отзывов о переданном продукте:
<?=ReviewList::widget(['itemId' => $model->id]);?>

Выведет форму добавления отзыва о продукте:
<?=ReviewForm::widget(['model' => $model]);?>
```
