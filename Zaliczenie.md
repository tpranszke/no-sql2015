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


Import trwał:


Rekordów zaimportowanych zostało:

Rekordy zliczono za pomocą polecenia:
```javascript
db.Com.count()
```
