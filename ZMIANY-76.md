# ZK Drogi 0.76 — odwrotny kierunek pobocza nie przerywa mapowania

- Naprawiono błąd zgłoszony dla 5CABA: opis brakującego odniesienia wywoływał PlanPoint na jeszcze nieprzypisanej polilinii biegnącej przeciwnie do kilometrażu. To powodowało wycofanie całego przypisania.
- Opisy luk są teraz pozycjonowane na bieżącej geometrii źródła z zachowaniem jego kierunku i parametrów odcinków. Odczyt nie korzysta z dawnych wiązań ani nie sortuje wierzchołków.
- Przed nowym przypisaniem niezarejestrowanej polilinii usuwane są odziedziczone zapisy wiązania i próbek. Istniejące zarejestrowane elementy zachowują swoje dane.
- Zwykły odwrotny kierunek rysowania jest obsługiwany. Rzeczywiste cofanie się wewnątrz polilinii nadal jest wykrywane i pomijane jako niejednoznaczne.

Po aktualizacji ponownie użyj Mapuj krawędzie, następnie Aktualizuj plan i przelicz model oraz skarpy.

Weryfikacja: 594 testy geometrii i polityk. Test regresji zawiera kilometraże 3014,8864182382931 → 3014,2625656362402 z logu użytkownika. Sprawdzono oba kierunki, końce i odcinek wewnętrzny oraz zachowanie kolejności źródła. Kompilacja z SDK BricsCAD. Pełnego ponownego mapowania w uruchomionym CAD jeszcze nie wykonano.
