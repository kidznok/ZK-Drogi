# ZK Drogi 0.78 — postęp mapowania krawędzi

- Mapuj krawędzie korzysta z tej samej kompaktowej karty postępu co modelowanie. Jedna karta obejmuje skan DWG, analizę warstw i elementów, kolejne przebiegi doboru odniesień, zapis, symbole spadków i odświeżenie widoku.
- Liczniki pochodzą z przetwarzanych obiektów, elementów danego przebiegu lub symboli; procent dotyczy bieżącego etapu. Etapy bez licznika pokazują pasek animowany. Długie rzutowanie wierzchołków aktualizuje własny licznik.
- Karta pojawia się po 0,4 s, bez przejmowania fokusu, i znika po zakończeniu. Ukryj działa do końca całego polecenia, również po zatwierdzeniu przypisań podczas aktualizacji symboli. Nie oferuje anulowania w połowie operacji obejmującej osobne zatwierdzenia transakcji.
- Automatyczne rozpoznawanie warstw i późniejsze odświeżanie planu używają jednej karty. Analiza warstw i ręczne zatwierdzanie odniesień także mają postęp; karta nie pozostaje otwarta podczas wybierania opcji w oknie analizy.
- Usunięto zbędne ponowne rzutowanie wierzchołków przy czyszczeniu opisów, gdy dla elementu nie ma żadnych luk.
- RSENGINESTATUS wyświetla faktyczną wersję załadowanej biblioteki zamiast stałego napisu 0.30.

Analiza dostarczonego logu: operacja zakończyła się komunikatem Dodano: 11, elementów: 43. Nie odnotowano wycofania ani wyjątku. Pozostają pominięcia obiektów rzutowanych wielokrotnie na koniec osi oraz brakujące lub niejednoznaczne odniesienia. Postęp nie zmienia zasad doboru i nie oznacza, że wszystkie polilinie zostały przypisane.

Sprawdzenie: kompilacja z SDK BricsCAD; testy karty na odizolowanym pulpicie Windows obejmujące etapy mapowania, jedną kartę, rzeczywisty licznik przebiegu, Ukryj także podczas późniejszego odświeżania symboli oraz pozostałe zachowania karty. Pełnego mapowania z nową kartą w uruchomionym CAD jeszcze nie wykonano. API CAD nadal pracuje na głównym wątku; karta nie przenosi obliczeń do tła.
