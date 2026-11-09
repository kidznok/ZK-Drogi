# ZK Drogi 0.46 — Dodaj PI: krawędź nominalna nie blokuje operacji

- Naprawiono błąd „Nie można narysować krawędzi nominalnej z zadaną dokładnością”, który cofał dodawanie PI i inne aktualizacje planu.
- Przyczyną był skok normalnej przy ostrym PI lub wierzchołku polilinii: rekurencyjne próbkowanie oznaczenia poszerzenia próbowało zagęszczaniem usunąć skok, aż osiągało limit głębokości.
- W wierzchołkach stosowana jest wspólna normalna z połączeniem odcinków, z ograniczeniem nadmiernego wysunięcia przy prawie przeciwnych ramionach. Pomiędzy wierzchołkami punkt nominalnej krawędzi jest ciągły.
- Próbkowanie oznaczenia ma ograniczenie liczby operacji, głębokości i minimalnego kroku. Jeżeli mimo to wystąpi nieciągłość, pomocnicza linia dostaje lokalną przerwę zamiast błędnego ukośnego połączenia. Informacja trafia do logu; nie jest zgłaszany wyjątek cofający poprawną geometrię drogi.
- Nie zmieniono walidacji właściwej osi, dopasowania łuków, powiązań krawędzi/poboczy ani zapisanych szerokości i korekt. Tolerancja ciągłych fragmentów oznaczenia pozostaje 2 mm.

Weryfikacja: 419 testów obliczeniowych, w tym ostry narożnik, skok normalnej, rozdzielenie części bez fałszywej przekątnej, ograniczenie wysunięcia oraz odcinek 10 km. Kompilacja pluginu dla BricsCAD V26 i testy aktualizatora. Ponowienia operacji na rysunku użytkownika w natywnej sesji CAD jeszcze nie przeprowadzono.

Zamknij wszystkie sesje BricsCAD przed instalacją wersji 0.46. Po restarcie ponów Geometria osi → Dodaj PI. Poprzednia operacja zakończona tym błędem była cofana transakcyjnie. 3D i skarpy pozostają do osobnego przeliczenia.
