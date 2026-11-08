# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.38 — manipulatory na pasmach
- Trójkąty procentowe i żółte strzałki skarp z wypełnionym grotem.
- Tekst z natywną maską tła jako wielowierszowy, odblokowany atrybut bloku: osobny uchwyt tekstu, uchwyt położenia symbolu i linia odniesienia podążająca za tekstem.
- Strzałki pośrodku pasma skarpy; opisy podniesione nad końce powierzchni w widoku z góry i przeniesione na wierzch kolejności rysowania.
- Ruch napisu nie zmienia kilometrażu. Ruch symbolu jest odróżniany od przeniesienia napisu przez blok; zapisane osobno odsunięcia tekstu.
- Przycisk Manipulatory: skala opisów, wysokość tekstu i długość strzałki w mm na wydruku. Domyślnie 1:1000 / 2,5 mm / 3,5 mm; jednostki modelu: metry.
- Poprawione pierwsze położenie napisu procentowego bez podwójnego dodawania współrzędnych początku.

Po instalacji: Aktualizuj plan → Przelicz skarpy. Zaznacz blok i korzystaj z osobnych uchwytów symbolu oraz napisu. Początek i koniec skarpy pozostają granicami zakresu.

346 testów obliczeniowych i 12 aktualizatora przechodzi. Kompilacja z API BricsCAD V26 bez błędów. Maski i uchwytów tej wersji nie zweryfikowano jeszcze w natywnym CAD. Szczegóły: ZMIANY-AKTUALNE.md.

Zamknij wszystkie sesje BricsCAD przed instalacją. Wymagany BricsCAD V26 x64 i .NET Desktop Runtime 8.0.33+ z linii 8. Wersja: 0.38.
