# ZK Drogi 0.77 — skarpy wyłącznie przy parze jezdnia + pobocze

- Skarpa powstaje od zewnętrznej krawędzi pobocza tylko we wspólnym zakresie z powiązaną jezdnią o określonej wysokości. Pobocze również musi mieć poprawne powiązanie wysokościowe lub niweletę.
- Sama jezdnia nie tworzy skarpy. Samo pobocze nie tworzy skarpy, nawet jeżeli ma własną niweletę. Brak pary jest celową przerwą, nie błędem dowiązania do terenu.
- Zakresy są ustalane osobno dla lewej i prawej strony. Pobocze musi leżeć na zewnątrz swojej jezdni. Obsługiwane są kolejne odniesienia jezdni oraz pośredni zarejestrowany krawężnik.
- Tolerancja końców używana przy mapowaniu nie przedłuża skarpy poza faktyczny zakres jezdni. Luki w parze nie są mostkowane trójkątami.
- Przeliczanie usuwa wcześniejszą powierzchnię z niedozwolonych fragmentów. Definicje, ręczne proporcje i ukryte manipulatory pozostają zapisane; mogą ponownie działać, jeśli poprawna para wróci.
- Na granicach dozwolonych fragmentów dodawane są manipulatory z zachowaniem obowiązującej proporcji. Przekroje również pomijają zakresy bez pary.
- Zweryfikowany brak wymaganej pary jest poprawnym pustym wynikiem, a nie stale nieaktualną skarpą. Powrót pary oznacza konieczność ponownego przeliczenia.
- Gdy nie ma żadnej poprawnej pary, polecenie nie pyta o nową proporcję ani nie tworzy powierzchni. Przelicza istniejące definicje, aby usunąć nieaktualny wynik.
- Do próbkowania powierzchni pozostaje dotychczasowy krok skarpy i cechy geometrii; sprawdzanie dostępności pary nie zagęszcza powierzchni do wszystkich wierzchołków źródła.

Po aktualizacji użyj Przelicz skarpy; jeżeli nie było jeszcze definicji, wybierz Skarpy od poboczy.

Weryfikacja: 617 testów geometrii i polityk, w tym para/sama jezdnia/samo pobocze, brak wysokości, rzeczywiste zakresy i przerwy, obie strony, położenie na zewnątrz, przekroczenie krawędzi, niweleta częściowa, pośredni krawężnik, cykl wysokości i zachowanie ręcznych proporcji. Kompilacja z SDK BricsCAD. Pełnego przeliczenia na żywym rysunku po tej zmianie jeszcze nie wykonano.
