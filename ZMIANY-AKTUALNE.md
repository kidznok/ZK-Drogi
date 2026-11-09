# ZK Drogi 0.41 — paleta geometrii i naprawa próbkowania krawędzi

- Otwarcie „Geometria osi” (RSAXISEDIT / RSTRANSITION) nie przebudowuje planu ani opisów. Nie blokuje go błąd topologii innego elementu.
- Usunięto przyczynę pozostawiania starej listy próbek po przejściu krawędzi na geometrię niepróbkowaną. Lista kilometraży i liczba wierzchołków nie rozchodzą się po tej operacji.
- „Zastosuj geometrię” odtwarza elementy z niespójną listą próbek z ich zapisanych powiązań szerokościowych. Zachowuje zapisane ręczne poszerzenia i reguły WR-D. Nie odczytuje nowych szerokości z uszkodzonego wyniku; nazwy odtworzonych elementów są podawane w wierszu poleceń.
- Oś, krawędzie i pobocza aktualizowane są w jednej transakcji po zmianie R, L₁ lub L₂. Pobocze zachowuje szerokość względem krawędzi. 3D i skarpy wymagają osobnego przeliczenia.
- Naprawa nie służy do zatwierdzania BREAK/TRIM próbkowanej krawędzi: niezapisane zmiany topologii wyniku zostaną zastąpione zapisanymi powiązaniami. Krótkie nowe elementy nadal należy dodawać osobnymi poliliniami.
- Biblioteka CAD ma numer wersji produktu 0.41, ułatwiający sprawdzanie zainstalowanego pliku.

Weryfikacja: kompilacja pluginu, testy obliczeniowe obejmujące osobną zmianę R/L₁/L₂, zachowanie ręcznego poszerzenia i szerokości pobocza, test panelu WPF i aktualizatora. Natywnego dokowania palety i zapisu w BricsCADzie nie potwierdzono — połączenie do sterowania aplikacją było niedostępne.

Zamknij wszystkie sesje BricsCAD przed instalacją wersji 0.41. Następnie Geometria osi → wskaż PI → R/L₁/L₂ → Zastosuj geometrię.
