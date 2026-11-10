# ZK Drogi 0.70 — przesuwanie uchwytów osi

Ruch natywnego uchwytu polilinii sterującej osi zachowuje zapisane promienie R oraz długości klotoid L1/L2. Usunięto niejawne uruchamianie doboru wszystkich automatycznych krzywych, które potrafiło cofnąć ruch nawet wtedy, gdy geometria z dotychczasowymi parametrami nadal się mieściła. Zwykłe odświeżanie planu również nie ponawia tego doboru bez edycji parametrów.

Dobór Auto / Proponuj pozostaje w edytorze Geometria osi. Zapisane flagi Auto nie są wyłączane przez ruch uchwytu. Po poprawnym ruchu dotychczasowy mechanizm aktualizuje zależne krawędzie i pobocza. Model 3D i skarpy nadal wymagają jawnego przeliczenia.

Walidacja matematycznej geometrii pozostaje aktywna. Jeżeli istniejące R/L po ruchu nie mieszczą się na ramionach albo sąsiednie krzywe kolidują, edycja jest odrzucana z przyczyną i przywróceniem ostatniego poprawnego przebiegu. Zmiana nie potwierdza zgodności parametrów z prędkością projektową.

565 testów geometrii/polityk: ruch końca z zachowaniem R/L i flag Auto, brak mutacji zapisanego stanu przed zatwierdzeniem, odrzucenie niemożliwej geometrii i oddzielenie dodania wierzchołka od przesunięcia. Kompilacja SDK BricsCAD V26. Pełnego ruchu uchwytu i podążania elementów w uruchomionym CAD po tej poprawce jeszcze nie wykonano.

Dodatkowo odczytano przez API kopię aktualnych parametrów osi użytkownika: 9 wierzchołków i 7 krzywych. W teście obliczeniowym wszystkie 36 przesunięć o 1 m (każdy wierzchołek w czterech kierunkach) przeszło bez zmiany R/L i flag Auto. Nie wykonywano tych ruchów w rysunku CAD.
