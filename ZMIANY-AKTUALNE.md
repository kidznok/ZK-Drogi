# ZK Drogi 0.51 — Auto / Ręcznie

- Oddzielne przełączniki Auto/Ręcznie pod R, L₁ i L₂ w wąskim oknie geometrii. Automatyczne pola są obliczane, a ręczne zachowują swoje wartości. Tryby zapisują się w DWG przy konkretnym PI. Proponuj włącza automatykę tych parametrów.
- Osobne przełączniki przy przechyłce i długościach ramp wejściowej oraz wyjściowej. Automat nie używa już stałego domyślnego 5%: dobiera pochylenie według R i prędkości, z zaokrągleniem w górę do 0,5%.
- Przy dużym promieniu zachowuje daszek, jeżeli pozwalają na to tabela, klasa drogi i szerokość jezdni. Dla niepodanej klasy nie zakłada dopuszczalności daszka 2%; dobiera rozwiązanie konserwatywne. Klasę i prędkość uzupełnia się w parametrach osi.
- Automatyczne rampy dobierane są blisko długości krzywych przejściowych, z kontrolą zakresu, szerokości, poszerzeń i granic dodatkowego pochylenia krawędzi. Pochylenia wynikowe w oknie nadal uwzględniają zapisaną niweletę. Brak miejsca lub rozwiązania spełniającego obsługiwane warunki daje komunikat zamiast wymuszonego wyniku.
- Po zastosowaniu zmiany geometrii automatyczne spadki i położenia manipulatorów są aktualizowane. Ręczne parametry i ręczne korekty etykiet nie są nadpisywane. Automatyczny promień uwzględnia także przechyłkę zadaną ręcznie.
- Nowe ustawienia ramp rozpoczynają pracę w trybie automatycznym. Istniejące ustawienia pozostają ręczne dla zachowania wcześniejszych decyzji projektanta — automatykę należy włączyć przełącznikami.
- Zapisane tryby geometrii reagują na zmianę PI i prędkości podczas aktualizacji planu. Obliczenia nie są ponawiane bez zmiany danych wejściowych.
- Model 3D i skarpy nadal wymagają osobnego przeliczenia. Zmiany geometrii najpierw zatwierdź w oknie geometrii, następnie otwórz rampy.

Zakres doboru: obsługiwane warunki WR-D-22-2:2023, tab. 7.1.2, 7.1.5 i 4.4.3.2. Nie jest to pełny audyt zgodności drogi — widoczność, odwodnienie i warunki lokalne wymagają osobnej oceny.
Źródło: https://www.gov.pl/attachment/489a909f-ca76-4841-b485-bcdfc88f9bd2

Weryfikacja: testy obliczeniowe oraz okna WPF (mieszane tryby, dobór przechyłki i ramp, zachowanie wartości ręcznych, zapis flag i zgodność ze starymi danymi). Działania na natywnym DWG w BricsCADzie jeszcze nie zweryfikowano. Instalacja po zamknięciu wszystkich sesji BricsCAD.
