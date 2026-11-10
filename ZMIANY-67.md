# ZK Drogi 0.67 — manipulatory po mapowaniu

Naprawiono przypadek, w którym po mapowaniu polilinii pozostawały wyłącznie opisy DBText zamiast bloków z symbolami spadku. Z logu: aktualizacja planu zatrzymywała się wcześniej w automatycznym rozwiązywaniu geometrii osi („Brak miejsca na automatyczną geometrię”), zanim wykonywane było tworzenie bloków.

Mapuj krawędzie odświeża teraz manipulatory na bieżącej geometrii w osobnej transakcji, bez uruchamiania automatycznego doboru łuków/klotoid ani przekształcania źródłowych krawędzi. Usuwa z kolejki edycji wyłącznie nowo utworzone przez mapowanie wiązania/źródła, aby nie uruchamiać po nich niepotrzebnej przebudowy osi. Włącza widoczność manipulatorów.

Ponowne Mapuj krawędzie naprawia także już przypisane elementy, nawet gdy nie ma nowych polilinii: ukrywa pomocnicze teksty i odtwarza bloki. Procentowy symbol to trójkąt między odniesieniem a krawędzią, z atrybutem tekstowym i istniejącą obsługą osobnego przesuwania symbolu i napisu. Automatyczne rozpoznawanie nowo rysowanych polilinii i ręczna tabela również tworzą bloki przed dalszym przeliczaniem planu.

Pomocnicze DBText nowych reguł projektu od początku są ukryte. Pozostają nośnikiem danych, a nie zastępstwem widocznego manipulatora.

Po aktualizacji: Nawigator → Krawędzie i elementy → Mapuj krawędzie. Nie dodaje ponownie istniejących reguł ani nie nadpisuje ręcznych spadków. Ta zmiana naprawia wyświetlanie i etap mapowania; błąd doboru geometrii osi nadal może blokować przeliczenie modelu 3D i wymaga osobnej korekty parametrów osi.

Weryfikacja: kompilacja ze SDK BricsCAD V26. Poprawka oparta na rzeczywistym stosie błędu użytkownika. Pełnego wyświetlenia bloków w uruchomionym CAD po zmianie jeszcze nie zweryfikowano.
