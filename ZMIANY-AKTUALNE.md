# ZK Drogi 0.60 — wiele dróg w jednym DWG i nowy nawigator

- W jednym DWG można rejestrować kilka niezależnych osi. Dodaj drogę pozwala wskazać kolejną własną polilinię; nie nadpisuje poprzedniej drogi. Każda ma osobne ustawienia, krawędzie, niweletę, rowy i przekroje. Dotychczasowy projekt pozostaje pierwszą drogą.
- Wąskie okno z rozwijanymi drogami i sekcjami: geometria osi, krawędzie, profil, model 3D, skarpy, przekroje. Bez nazwy pliku, z podpisem Vdp i oznaczeniem aktywnej drogi. Przyciski znajdują się przy odpowiedniej sekcji.
- Rozwinięcie innej drogi przełącza jej kontekst. Każde polecenie uruchomione z nawigatora zawiera identyfikator drogi; wybór rowu otwiera jego niweletę. Polecenia wpisywane ręcznie działają na aktywnej drodze.
- Dane wszystkich dróg i ich ustawienia zapisują się w katalogu tego samego DWG. Wygenerowane obiekty mają właściciela, a indeksy wyników i warstwy modeli są rozdzielone. Pełna przebudowa modelu, profilu, skarp lub kreskowania jednej drogi nie powinna usuwać wyników innych dróg.
- Edycja uchwytami osi/elementów innej drogi jest rozpoznawana po właścicielu. Wspólna edycja kilku dróg jest obsługiwana kolejno w ich kontekstach.
- Aktualność modelu, profilu, skarp i przekrojów wynika z porównania danych wejściowych z zapisem ostatniego udanego przeliczenia. Bursztynowy znacznik i Przelicz dla zmian; czerwony znacznik dla błędu. Podsumowanie jest widoczne także na zwiniętej drodze.
- Wyniki ze starszych wersji bez zapisu danych przeliczenia pokazują Do przeliczenia — nie są uznawane automatycznie za zweryfikowane. Po aktualizacji przelicz potrzebne wyniki raz.
- Usunięcie wygenerowanych fragmentów jest wykrywane podczas pracy dodatku. Samo przesunięcie tekstu etykiety skarpy nie zmienia stanu geometrii. Odczyt nawigatora nie generuje modeli; skróty danych są buforowane do zmiany źródeł.
- Po zmianie zewnętrznego terenu przeładuj Xref, następnie przelicz skarpy/przekroje. Podpinanie osi jako referencji pozostaje w dotychczasowym trybie pustego projektu; ta zmiana dotyczy kilku własnych osi w jednym DWG.

Weryfikacja: 530 testów obliczeniowych i logiki izolacji danych, testy okien z trzema drogami, akcjami przypisanymi do osi i stanami aktualności. Kompilacja z SDK BricsCAD bez błędów i ostrzeżeń. Testy te nie zastępują testu natywnego DWG: pełnego przebiegu trzech dróg z geometrią 3D w uruchomionym BricsCADzie jeszcze nie zweryfikowano.

