Zadanie zostało wykonane na komputerze stacjonarnym. Specyfikacja znajduje się w pliku [README.md](https://github.com/Enessetere/no-sql2015/blob/master/README.md).

# EDA
## Import DB do MongoDB i PostgreSQL
Do wykonania tego zadania wybrałem bazę komentarzy Reddit, która po rozpakowaniu zajmowała około 29.5GB.
##Import do MongoDB
W celu zaimportowania bazy danych użyłem tego polecenia:
```javascript
mongoimport --db RDB --collection Com --file RC_2015-01.json
```

W trakcie importu, tak prezentowało się wykorzystanie zasobów:

![](http://i.imgur.com/TFsTyVI.png)

Import trwał:

![ ](http://i.imgur.com/qyBacdC.png)

Rekordów zaimportowanych zostało:

![](http://i.imgur.com/D9x3gnJ.png?1)

Rekordy zliczono za pomocą polecenia:
```javascript
db.Com.count()
```

##Import do PostgreSQL
W celu zaimportowania bazy danych użyłem tego polecenia:


W trakcie importu, tak prezentowało się wykorzystanie zasobów:


Import trwał:

Rekordów zaimportowanych zostało:

Rekordy zliczono za pomocą polecenia:


## Porównanie

- Czas importu:

- Użycie zasobów:
 
- Wyniki:


# GeoJSON

Do utworzenia mapy GeoJSON wykorzystałem [geojson.io](http://geojson.io/). Wykonałem mapkę z zaznaczeniem Pubów w Gdańsku. Jest możliwe, że część pominąłem.

*Mapa Pubów*

![](http://i.imgur.com/PO1hKUj.jpg)

DB zostało zaimportowane do Mongo za pomocą polecenia:
```javascript
mongoimport --db PDB --collection Pub --file map.json
```

Przykładowy rekord, razem z wywołaniem na SS poniżej:

![](http://i.imgur.com/oJemkkh.png?1)

