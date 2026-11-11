# ZK Drogi 0.81 — reguły sąsiedztwa i ciągłość krawędzi

## Obsługa
1. Ustawienia → Mapowanie warstw: określ typ każdej warstwy (w tym Obrzeze).
2. Domyślne reguły lub Ustawienia → Reguły sąsiedztwa: ustal pary Od / Do, spadek procentowy lub różnicę Z w metrach oraz tolerancję ciągłości (domyślnie 0,25 m). Reguły są zapisywane w ustawieniach drogi w DWG.
3. Wybierz Mapuj krawędzie. Potem Utwórz / odśwież 3D i Przelicz skarpy.

## Zmiany
- Rozpoznawanie warstwy i reguły wysokościowe są rozdzielone. Automat analizuje najbliższego sąsiada od strony osi, osobno na L/P i odcinkami kilometrażu. Przykłady: oś → jezdnia −2%, jezdnia → pobocze −8%, krawężnik → pobocze −8%, obrzeże → krawężnik +2%. Wartości można edytować.
- Jeden element może korzystać z kilku polilinii odniesienia i różnych reguł na kolejnych zakresach. Współliniowy krawężnik na krawędzi jezdni jest rozpoznawany jako zewnętrzna granica tej pary.
- Reguły stosuje zarówno Mapuj krawędzie, jak i analiza Wybierz odniesienia oraz rozpoznawanie nowo rysowanych elementów. Opcjonalnie można wyłączyć mapowanie sąsiedztwa i wrócić do starszego Parent / Value z tabeli warstw.
- Fragmenty tego samego typu mogą tworzyć logiczny ciąg, jeśli ich kilometraże i końce w planie mieszczą się w tolerancji. Polilinie źródłowe pozostają oddzielne. Rozgałęzienia, większe przerwy i niejednoznaczne pokrycie nie są łączone przez zgadywanie.
- Nie wyświetla się automatycznych manipulatorów na styku kolejnych fragmentów, gdy typ odniesienia i reguła pozostają takie same. Wewnętrzne reguły obliczeniowe pozostają przy każdym fragmencie. Rzeczywiste zmiany wartości i ręczne manipulatory pozostają widoczne.
- Model 3D dostaje krótkie łączniki między zgodnymi fragmentami drogi w granicach tolerancji. Łączniki są zastępowane przy kolejnej przebudowie, zamiast być dokładane wielokrotnie.
- Przy ciągłym poboczu dopuszczalna przerwa między jego fragmentami odniesienia jezdni nie przerywa warunku jezdnia + pobocze dla obliczeń skarpy. Nadal sama jezdnia lub samo pobocze nie tworzą skarpy. Nie uzupełnia się braku terenu ani niwelety.
- Przy pierwszym odczycie starszego projektu spójne domyślne spadki z mapowania warstw są przenoszone do reguł sąsiedztwa. Migracja jest jednorazowa; późniejsza edycja reguł nie jest nadpisywana.
- Nowe reguły automatyczne są oznaczone. Ręczne spadki, przechyłki i rampy są chronione przed zastąpieniem podczas ponownego mapowania. Dla dawnych etykiet bez znacznika automat może przejąć jedynie początkową regułę nadal równą domyślnej wartości warstwy; pozostałe zachowuje i raportuje.
- Zmieniono wersję algorytmu modelu — pierwsza przebudowa po aktualizacji jest pełna.

## Weryfikacja i ograniczenia
661 testów geometrii i polityk, w tym 10 km / 100 fragmentów, przerwa 20 cm, ograniczenie całej przerwy tolerancją, różne strony, obrzeże przed krawężnikiem, zbieżna geometria jezdni i krawężnika, niejednoznaczność oraz ciągłość warunku skarpy. Testy WPF na odizolowanym pulpicie obejmują zapis reguł, przecinek dziesiętny i odrzucenie błędnej tolerancji. Kompilacja z SDK BricsCAD.
Nie wykonano pełnego mapowania i przebudowy na aktualnym DWG użytkownika. Niewłaściwy kilometraż źródła i brak reguły nadal wymagają korekty lub jawnego wskazania. Łączniki dotyczą modelu drogi; osobne definicje skarp zachowują swoje zakresy i nie są scalane z innymi definicjami przez zgadywanie.