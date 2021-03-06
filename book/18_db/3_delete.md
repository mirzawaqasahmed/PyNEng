### DELETE

Оператор delete используется для удаления записей.

Как правило, он используется вместе с оператором where.

Например, таблица switch выглядит так:
```sql
sqlite> SELECT * from switch;
mac             hostname    model       location           mngmt_ip    mngmt_vid
--------------  ----------  ----------  -----------------  ----------  ----------
0010.D1DD.E1EE  sw1         Cisco 3850  London, Green Str  10.255.1.1  255
0020.A2AA.C2CC  sw2         Cisco 3850  London, Green Str  10.255.1.2  255
0040.A4AA.C2CC  sw4         Cisco 3850  London, Green Str  10.255.1.4  255
0050.A5AA.C3CC  sw5         Cisco 3850  London, Green Str  10.255.1.5  255
0060.A6AA.C4CC  sw6         C3750       London, Green Str  10.255.1.6  255
0070.A7AA.C5CC  sw7         Cisco 3650  London, Green Str  10.255.1.7  255
0030.A3AA.C1CC  sw3         Cisco 3850  London, Green Str  10.255.1.3  255
0080.A8AA.C8CC  sw8         Cisco 3850  London, Green Str  10.255.1.8  255

```

Удаление информации про коммутатор sw8 выполняется таким  образом:
```sql
sqlite> DELETE from switch where hostname = 'sw8';
```

Теперь в таблице нет строки с коммутатором sw8:
```sql
sqlite> SELECT * from switch;
mac             hostname    model       location           mngmt_ip    mngmt_vid
--------------  ----------  ----------  -----------------  ----------  ----------
0010.D1DD.E1EE  sw1         Cisco 3850  London, Green Str  10.255.1.1  255
0020.A2AA.C2CC  sw2         Cisco 3850  London, Green Str  10.255.1.2  255
0040.A4AA.C2CC  sw4         Cisco 3850  London, Green Str  10.255.1.4  255
0050.A5AA.C3CC  sw5         Cisco 3850  London, Green Str  10.255.1.5  255
0060.A6AA.C4CC  sw6         C3750       London, Green Str  10.255.1.6  255
0070.A7AA.C5CC  sw7         Cisco 3650  London, Green Str  10.255.1.7  255
0030.A3AA.C1CC  sw3         Cisco 3850  London, Green Str  10.255.1.3  255

```

