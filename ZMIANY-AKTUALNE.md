# ZK Drogi 0.79 — granice próbkowania modelu 3D

- Naprawiono przypadek Limit próbkowania: km 2748.3149224865124..2748.314922586951. Algorytm nie dzieli dalej odcinków o długości do 0,000001 m; zachowuje jednak wymagane punkty graniczne.
- Błąd cięciwy jest oceniany tylko na faktycznej części wspólnej z zakresem elementu. Tolerancja sprawdzania obecności nie powoduje odczytywania nieistniejącego fragmentu za końcem krawędzi.
- Końce i środek badanego odcinka korzystają z tej samej aktywnej reguły/referencji wybranej wewnątrz odcinka. Rzeczywisty skok wysokości na granicy pozostaje zachowany z obu stron i nie jest traktowany jak krzywizna wymagająca ciągłego zagęszczania.
- W podążaniu pobocza za odcinkami jezdni niemal zbieżne dodatkowe kilometraże są scalane z istniejącą siatką punktów sterujących. Nie powstają pary punktów szerokości odległe o mniej niż tolerancja walidacji.
- Dotychczasowe ograniczenia głębokości i liczby próbek pozostają aktywne dla rzeczywiście nierozwiązywalnej geometrii. Nieprawidłowe i nieskończone wyniki nadal zgłaszają błąd.
- Zmieniono wersję algorytmu modelu; pierwsze przeliczenie po aktualizacji przebuduje model w całości, aby nie mieszać starych i nowych fragmentów.

Po aktualizacji wybierz Utwórz / odśwież 3D. Następnie przelicz skarpy, jeśli zmienił się model.

Weryfikacja: 626 testów geometrii i polityk; regresja zawiera dokładny przedział ze zrzutu, obustronną granicę skoku wysokości, przycięcie do zakresu, zachowanie limitów i niemal zbieżne węzły szerokości. Kompilacja z SDK BricsCAD bez błędów. Dostęp przez API do aktualnego rysunku był niedostępny; pełnej przebudowy na żywym DWG po tej poprawce jeszcze nie wykonano.
