# Type Data Database MySQL di File Migrasi Yii2

```
- int ---> $this->integer();
- varchar ---> $this->string(panjang);
- bigint ---> $this->bigInteger();
- int and primary ---> $this->primaryKey();
- bigint and primary ---> $this->bigPrimaryKey();
- date ---> $this->date();
- datetime ---> $this->dateTime();
- decimal ---> $this->decimal(jumlahangka, angkadibelakangkoma);
- text ---> $this->text();
- tinyint ---> $this->tinyInteger

```