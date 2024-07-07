# Active Record Yii2

adalah salah satu metode pembungkusan query yang ada di yii2

```php
<?php

class Model extends ActiveRecord {

}
```

banyak hal yang bisa anda lakukan dengan menggunakan active record ini

## Relation

### HasOne

### HasMany

## Static

### updateAllCounters

```
$counterAdd = 1;
$condition = [
    ['and',
    ['>', 'id', 10],
    ['=', 'staff_id',$staff_id],
];

Model::updateAllCounters(['id' => $counterAdd],$condition);
```

## FindOne

### UpdateCounter

### Save

## Find

### WHERE

**OPERATOR**

```php
$model->where(['>=', 'id', 10]);// produce, WHERE id >= 10
```

**LIKE**

```php
$model->where(['LIKE', 'product_id', 'val']);
$model->where(['LIKE', 'product_id', ['val', 'val2']]); // produce, product_id LIKE %val% AND product_id LIKE %val2%
$model->where(['LIKE', 'name', '%tester', false]); // will generate name LIKE '%tester'.
```

**IN**

```php
$model->where(['product_id', ['A', 'B', 'C']]);
$model->where(['in', 'product_id', $arrayList]);
```

ref:

- https://stackoverflow.com/questions/31271499/yii2-where-in-with-active-record
- https://www.yiiframework.com/doc/api/2.0/yii-db-queryinterface#where()-detail

**BETWEEN**

```php
$model->andWhere(['between', 'tahun', $exp[0], $exp[1]]);
```

**WHERE IS NULL**

```php
<?php Product::find()->where(['fieldname' => NULL])->all(); ?>
<?php Product::find()->where('fieldname IS NULL')->all(); ?>
```

ref :

- https://forum.yiiframework.com/t/active-record-where-not-null/71291/3

**WHERE NOT NULL**

```php
<?php Product::find()->where('fieldname IS NOT NULL')->all(); ?>
```

### SUM

### COUNT

### ALL

### ALL-AS Array
