# MV (Move) dan CP (Copy)

bayangkan struktur folder Anda seperti ini :

```
|parent
    |--child1
    |--child2
    |--grandChild1
    |--grandChild2
    |--grandChild3
    |--grandChild4
    |--grandChild5
    |--grandChild6
```

dan anda ingin menatannya seperti ini.

```
|parent
    |--child1
    |   |--grandChild1
    |   |--grandChild2
    |   |--grandChild3
    |   |--grandChild4
    |   |--grandChild5
    |   |--grandChild6
    |--child2
```

pada kasus ini, kamu perlu mengecualikan 2 direktori **child1** and **child2**, dan memindahkan sisanya ke child1.

gunakan

```
mv !(child1|child2) child1
```

perintah diatas akan memindahkan semuanya ke child1
