# ZK Drogi 0.68 — model 3D z zapisanej osi

Naprawiono zatrzymanie budowy modelu 3D komunikatem „Brak miejsca na automatyczną geometrię”, gdy nie było nowej edycji wierzchołków osi. Przy budowie modelu dotychczas wykonywany był ponowny dobór R i klotoid według prędkości, szerokości i ograniczeń ramp, zanim rozpoczęło się liczenie wysokości. Niepowodzenie propozycji blokowało model z już zapisanej osi.

Utwórz / odśwież 3D oraz pełne/lokalne przeliczenie modelu korzystają teraz z bieżącej zapisanej geometrii i nie uruchamiają niejawnego ponownego doboru jej parametrów. Dobór i zmiana R/L pozostają w Geometrii osi i jej dotychczasowym przebiegu edycji. Zmiany niwelety, spadków i szerokości są nadal uwzględniane przy modelowaniu.

Faktycznie zmieniony uchwyt osi nadal podlega istniejącemu rozwiązaniu geometrii i walidacji: nie ignorujemy niezatwierdzonej lub błędnej edycji punktów. Zmiana nie oznacza potwierdzenia zgodności istniejącej geometrii z prędkością projektową.

Po aktualizacji wybierz ponownie Utwórz / odśwież 3D. Poprawna przebudowa zastąpi zapamiętany błąd modelu w Nawigatorze.

Kompilacja ze SDK BricsCAD V26. Poprawka dotyczy gałęzi wskazanej w rzeczywistym logu użytkownika. Pełnej budowy 3D w uruchomionym CAD po zmianie jeszcze nie wykonano.
