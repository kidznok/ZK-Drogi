# ZK Drogi 0.44 — dodawanie PI, przesuwanie profilu i śledzenie na planie

## Dodaj PI w geometrii osi
- Nowy przycisk + Dodaj PI w okienku geometrii oraz polecenie RSAXISADDPI.
- Wskaż odcinek łamanej PI, następnie nowe położenie punktu. Program dodaje wewnętrzny wierzchołek, aktualizuje plan i wybiera go w edytorze. Wybierz łuk lub klotoida–łuk–klotoida, wpisz R/L₁/L₂ i Zastosuj.
- Obsługiwana jest również oś będąca pojedynczą prostą z dwoma punktami: otwórz Geometria osi i użyj Dodaj PI. Dodawanie jest oddzielnym zatwierdzanym krokiem, więc Cofnij parametry nie usuwa dodanego punktu; wycofanie kroku przez CAD UNDO.
- Istniejące łuki zachowują tożsamość i osobne długości klotoid. Krawędzie, pobocza, ręczne poszerzenia, reguły, profile i zakresy skarp otrzymują dodatkową kotwicę kilometrażu. Nie są przeliczane przez błędne indeksy po zmianie liczby PI.
- Jeżeli istniejące łuki po zmianie ramion nie mieszczą się, dodanie jest odrzucane przed zapisem. ESC podczas wskazywania nie zmienia DWG. Zapis osi i zależnego planu pozostaje w jednej transakcji.
- Dodawanie przyciskiem nie porzuca poprawnego szkicu R/L₁/L₂; uwzględnia go w tej samej operacji. 3D i skarpy wymagają jawnego przeliczenia.

## Profil
- Przeciąganie środkowym przyciskiem myszy przesuwa widok w poziomie i pionie, bez zmiany PVI. Alternatywnie włącz Przesuń i przeciągaj lewym przyciskiem. Cały profil przywraca cały zakres i zeruje przesunięcie pionowe.
- Pozostają kółko do zbliżenia i Shift+kółko do przesuwania poziomego.
- Śledź na planie: ruch kursora po profilu oraz wybór PVI przekazuje kilometraż do tymczasowego znacznika na osi w CADzie. Nie zmienia rzutni ani nie dodaje obiektów do DWG. Wyłączenie, opuszczenie wykresu i zamknięcie edytora usuwa znacznik. Odświeżanie ograniczone do ok. 28 razy na sekundę.
- Docelowy nowy wygląd dużego edytora profilu jest osobną propozycją; ta wersja dodaje sterowanie widokiem i śledzenie do aktualnego okna.

Weryfikacja: 412 testów obliczeniowych, testy rzeczywistych paneli WPF osi i profilu, w tym trasa przycisku Dodaj PI, przesuwanie obu osi bez edycji geometrii i zdarzenia śledzenia. Testy aktualizatora i kompilacja API BricsCAD V26. Natywne działanie znacznika i dodania PI w otwartym BricsCADzie nie zostało jeszcze zweryfikowane.

Zamknij wszystkie sesje BricsCAD przed instalacją wersji 0.44.

## Kolory osi na planie
- Jednolity podział: prosta ACI 1 (czerwona), łuk kołowy ACI 2 (żółty), klotoidy ACI 30 (pomarańczowe), kreska–kropka. Obsługa również natywnych łuków polilinii.
- Aktualizacja przywraca widoczność i kolejność rysowania warstwy stylu. Sygnatura uwzględnia parametry osi i niwelety.
- Kolorowa reprezentacja jest rysowana także na wysokości niwelety z odstępem graficznym 2 cm, żeby czerwona oś modelu 3D nie zasłaniała jej w widoku cieniowanym. Nie zmienia to geometrii obliczeniowej osi ani rzędnych drogi.