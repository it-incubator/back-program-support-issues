## Collation
студент обратился с проблемой неправильного порядка сортировки по регулярному выражению при запросу в PostgreSQL
проблема была в неверно заданом правиле сортировки было "UTF-8" стало "C.UTF-8"

полезные ссылки 
- ***[таблица кодов ASCII](https://theasciicode.com.ar/ascii-printable-characters/capital-letter-t-uppercase-ascii-code-84.html)***
- ***[ссылка по доке JS по определению номера символа в ASCII кодировке](https://www.w3schools.com/jsref/tryit.asp?filename=tryjsref_charcodeat1)***
- ***[Ссылка на доку постгрес по установке значений locale и collation by default](https://www.postgresql.org/docs/current/locale.html)***
- ***[таблица utf-8 кодов](https://www.utf8-chartable.de/)***