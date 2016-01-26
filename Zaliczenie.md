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

## Piont

Załóżmy, że umówiliśmy się ze znajomymi na dworcu w Gdańsku Głównym, ale nasz ulubiony Pub jest zamknięty. Dzięki wprowadzeniu nowej wartości oraz temu zapytaniu, możemy znaleźć pobliskie puby w odległości 15 mil.

```javascript
var GdaDwG = {
 "type" : "Point",
	"coordinates" : [
		18.644378185272213,
		54.35639370678616
	]
}

db.Pub.find({geometry : { $geoWithin : { $centerSphere : [[18.644378, 54.3563394], 15/3963.2]}}})
```

## Polygon

A teraz załóżmy, że umówiliśmy się w jakimś Pubie przy ul. Długiej. Dzięki temu zapytaniu wyodrębnimy Puby znajdujące się przy ulicy Długiej.

```javascript


db.Pub.find({
 geometry : {
  $geoWithin : {
   "geometry": {
        "type": "Polygon",
        "coordinates": [
          [
            [
              18.647457361221313,
              54.34880916171055
            ],
            [
              18.648948669433594,
              54.35068510695288
            ],
            [
              18.6518132686615,
              54.34983468905395
            ],
            [
              18.65349769592285,
              54.34913433168772
            ],
            [
              18.656147718429565,
              54.34865908239178
            ],
            [
              18.654967546463013,
              54.34694563798999
            ],
            [
              18.647457361221313,
              54.34880916171055
            ]
          ]
        ]
       }
      }
     }
    }
  )
```
