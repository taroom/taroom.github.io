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

### SUM

### COUNT

### ALL

### ALL-AS Array
