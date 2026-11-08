# ZK Drogi 0.35 — edytor niwelety: droga i rowy

- Osobny edytor WPF: wspólny wykres drogi i rowów, wybór aktywnej niwelety, pasma rzędnych projektowanych, terenu, pochylenia i geometrii.
- Edycja PVI w tabeli, polami parametrów oraz przeciąganiem. Dodawanie/usuwanie wewnętrznych PVI, cofanie zmian w oknie; zbliżanie kółkiem myszy i przesuwanie widoku z Shift.
- Kołowe łuki pionowe zadawane promieniem R; kontrola kolejności PVI, długości stycznych i nachodzenia łuków. Z, i, T, długość łuku, PŁ/KŁ w panelu wybranego PVI.
- Niezależna niweleta każdego zarejestrowanego rowu. Użyj „Dodaj rów”, wskaż własną polilinię i nazwij ją, potem otwórz edytor.
- „Zastosuj i aktualizuj DWG” zapisuje PVI i promienie w DWG oraz odświeża wykres z pasmami. To samo obliczenie wysokości obsługuje drogę, rowy i model 3D; PŁ/KŁ są stacjami charakterystycznymi.
- „Teren do profilu”: odczyt 3DFACE z wybranego Xrefa i warstwy, z krokiem próbkowania. Braki pokrycia nie są łączone przez długie luki.
- Istniejąca niweleta poliliniowa jest wczytywana do edytora. DWG zachowuje niewidoczny profil zgodności. Publikacja osi zawiera również dokładne PVI i promienie.
- Modyfikacje w oknie nie przebudowują CAD podczas przeciągania. Po zatwierdzeniu wybierz „Utwórz / odśwież 3D”, następnie „Przelicz skarpy”. Rzutnia pozostaje bez zmian.

## Kolejność pracy
1. Wskaż oś i utwórz krawędzie/pobocza.
2. Opcjonalnie „Dodaj rów”: wskaż polilinię rowu, odniesienie i nazwę. Powtórz dla drugiej strony.
3. Opcjonalnie „Teren do profilu”: Xref z 3DFACE, warstwa, krok.
4. „Edytor niwelety”: przy pierwszym otwarciu wskaż miejsce wykresu DWG. Wybierz Drogę lub konkretny rów.
5. Ustaw PVI i R. R=0 oznacza załamanie. Skrajne kilometraże odpowiadają zakresowi elementu w planie.
6. Zastosuj, potem odśwież 3D i skarpy.

## Zakres i weryfikacja
- Łuki kołowe pionowe; brak parabol oraz automatycznej weryfikacji przepisów/WR-D.
- Teren jest zapisanym przekrojem próbkowanym. Po zmianie osi lub Xrefa pobierz go ponownie; zmiana osi usuwa nieaktualne próbki.
- Nie jest to edycja niwelety uchwytami na wynikowym wykresie DWG. PVI edytuje się w osobnym oknie.
- Kompilacja oraz testy geometrii i rzeczywistych kontrolek WPF bez interakcji z ekranem. Integracja w natywnym BricsCAD V26 wymaga jeszcze sprawdzenia na kopii DWG.
- Zmiany dotyczą profilu; nie zawierają poprawek wcześniejszego zgłoszenia o nakładających się skarpach i położeniu ich etykiet.

Zamknij wszystkie sesje BricsCAD przed instalacją. Wymagany BricsCAD V26 x64 i .NET Desktop Runtime 8. Wersja produktu: 0.35.

