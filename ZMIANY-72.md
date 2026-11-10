# ZK Drogi 0.72 — kompaktowy postęp operacji

- Karta 252 × 94 px przy 100% DPI, na podstawie okna ZK Przejazd 0.80. Ciemne tło, turkusowy pasek, nazwa operacji, etap i procent bez części dziesiętnej.
- Pojawia się dopiero po 0,4 s; krótkie operacje nie powodują mignięcia. Znika po zakończeniu, przełączeniu lub zamknięciu rysunku.
- Podłączona do odświeżania planu i krawędzi, przebudowy modelu 3D oraz przeliczania skarp i rowów. Zagnieżdżone operacje korzystają z jednej karty.
- Procent wynika z liczby przetworzonych elementów lub próbek bieżącego etapu. Etapy bez znanej liczby prac pokazują animowany pasek.
- Automatyczny plan: przycisk Ukryj, bez przejmowania fokusu. Ukryta karta nie wraca w tej samej operacji.
- Przebudowa 3D i skarp: Anuluj sprawdzane w punktach kontrolnych przed zatwierdzeniem transakcji. Anulowanie wycofuje niezapisany wynik; nie jest błędem w Nawigatorze.

Sprawdzenie: kompilacja z SDK BricsCAD, testy karty na osobnym niewidocznym pulpicie Windows (opóźnienie, wymiary, brak aktywacji, procenty, animacja, Ukryj, Anuluj, przełączenie/zamknięcie rysunku i automatyczne znikanie). Nie wykonano prób przebudowy ani anulowania na żywym rysunku w BricsCAD.

Ograniczenie: karta ma osobny wątek interfejsu, lecz operacje API CAD nadal wykonują się na głównym wątku CAD. Nie dodaje blokady modalnej, ale nie przenosi obliczeń do tła. Anulowanie następuje po dojściu do najbliższego punktu kontrolnego.
