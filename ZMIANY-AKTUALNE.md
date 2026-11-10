# ZK Drogi 0.66 — walidacja zakresu przed mapowaniem

Naprawiono wycofywanie całego automatycznego mapowania, gdy jedna z nowych polilinii ma powtarzający się albo cofający kilometraż. Zgłoszony przypadek: zatoka 5C9BD z kolejnymi punktami o stacji 3014.8864182382931 na końcu osi.

Przed zapisaniem wiązania sprawdzane są stacje wierzchołków, włącznie z przyciąganiem do stacji wierzchołków osi. Wadliwa nowa polilinia jest pomijana z identyfikatorem, warstwą i wskazaniem przyczyny. Pozostałe poprawne polilinie nadal są przypisywane. Tabela Wybierz odniesienia również oznacza taką polilinię jako niegotową do dodania.

Nie sortujemy wierzchołków, nie przycinamy źródła ani nie rozdzielamy sztucznie dwóch takich samych kilometraży. Jeżeli polilinia wychodzi poza początek/koniec osi, należy skrócić lub podzielić jej fragment do zakresu osi albo wydłużyć oś. Krawędź biegnąca poprzecznie lub wracająca względem kilometrażu wymaga podziału; obecny model wiązania opisuje jedną szerokość w danym kilometrażu.

Po aktualizacji wybierz ponownie Mapuj krawędzie. Poprawne przypisania zostają zachowane; sprawdź komunikaty Pominięto dla pozostałych fragmentów.

Weryfikacja: 561 testów geometrii/polityk, w tym regresja z dokładną stacją ze zgłoszenia, powtórzenie stacji na początku i wewnątrz osi, cofnięcie kilometrażu oraz poprawna krótka zatoka. Kompilacja SDK BricsCAD V26. Pełnego mapowania w uruchomionym CAD po zmianie jeszcze nie zweryfikowano.
