NBD Ćwiczenia 5 – Riak
Na maszynie wirtualnej Riak uruchamia się automatycznie (pojedyncza instancja), dostępny jest na porcie 8098 
Jako rozwiązanie należy wysłać jeden plik tekstowy zawierający ponumerowane polecenia curl i dodatkowo do każdego z zadań tekstowy plik wynikowy zawierający odpowiedź z serwera (wraz z nagłówkami, więc należy w curl użyć switcha -i) 
 
1.	Umieść w bazie (nazwa bucketa ma być Twoim numerem indeksu poprzedzonym literą „s”)
	 5 wartości, gdzie każda z nich ma być dokumentem json mającym 4 pola
	 co najmniej dwóch różnych typów.
	 
	 curl -XPOST -i -H "Content-Type: application/json" -d '{"manufacturer": "VV", "model": "Golf", "horsePower": 115, "imported": true }' http://localhost:8098/buckets/s16852/keys/car1
	 curl -XPOST -i -H "Content-Type: application/json" -d '{"manufacturer": "Ford", "model": "Fiesta", "horsePower": 98, "imported": false }' http://localhost:8098/buckets/s16852/keys/car2
	 curl -XPOST -i -H "Content-Type: application/json" -d '{"manufacturer": "Fiat", "model": "Multipla", "horsePower": 90, "imported": true }' http://localhost:8098/buckets/s16852/keys/car3
	 curl -XPOST -i -H "Content-Type: application/json" -d '{"manufacturer": "Honda", "model": "Civic", "horsePower": 80, "imported": false }' http://localhost:8098/buckets/s16852/keys/car4
	 curl -XPOST -i -H "Content-Type: application/json" -d '{"manufacturer": "Ford", "model": "C-max", "horsePower": 150, "imported": true }' http://localhost:8098/buckets/s16852/keys/car5

2.	Pobierz z bazy jedną z dodanych przez Ciebie wartości. 

	curl -i http://localhost:8098/buckets/s16852/keys/car2

3.	Zmodyfikuj jedną z wartości – dodając dodatkowe pole do dokumentu. 

	curl -XPUT -i -H "Content-Type: application/json" -d '{"manufacturer": "Ford", "model": "Fiesta", "horsePower": 98, "imported": false, "maxSpeed": 180 }' http://localhost:8098/buckets/s16852/keys/car2

4.	Zmodyfikuj jedną z wartości – usuwając jedną pole z wybranego dokumentu. 
	
	curl -XPUT -i -H "Content-Type: application/json" -d '{"manufacturer": "Ford", "model": "Fiesta", "horsePower": 98, "maxSpeed": 180 }' http://localhost:8098/buckets/s16852/keys/car2

5.	Zmodyfikuj jedną z wartości – zmieniając wartość jednego z pól.  
6.	Usuń jeden z dokumentów z bazy. 
7.	Spróbuj pobrać z bazy wartość, która nie istnieje w tej bazie. 
8.	Dodaj do bazy 1 dokument json (zawierający 1 pole), ale nie specyfikuj klucza. 
9.	Pobierz z bazy element z zadania 8. 
10.	Usuń z bazy element z zadania 8. 
