# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

Wersja 0.31 usuwa potwierdzony w logu błąd „Layer is locked” przy odświeżaniu kolorowej reprezentacji osi, który blokował przesuwanie PI oraz uruchomienie skarpy. Działanie poprawki na rysunku użytkownika wymaga jeszcze potwierdzenia. Wersja 0.30 upraszcza wstążkę do przebiegu: oś → krawędzie i spadki → profil → model 3D → skarpy. Osobny przycisk Aktualizacja programu otwiera menedżer GitHub Releases.

- Wskazanie własnej osi, oznaczenie prostych na czerwono, łuków na żółto i klotoid programu na pomarańczowo, kreska-kropka.
- Krawędzie i opcjonalne pobocza z domyślnymi regułami -2% / -8% oraz manipulatorami na końcach.
- Niweleta, model 3D, skarpy do terenu 3DFACE z Xrefa.
- Zmiana proporcji skarpy na przedziale, np. 1:2, z powrotem do poprzedniej wartości za końcem przedziału; blokowe manipulatory i osobno przesuwany tekst.

Zamknij cały BricsCAD przed instalacją. Wymagany .NET Desktop Runtime 8.0.33 lub nowszy z linii 8. Instalator niepodpisany cyfrowo. Zachowaj kopię DWG. Nie ładuj starszych silników do tej samej sesji.

265 sprawdzeń geometrii/logiki i 12 aktualizatora przechodzi. Nowej wstążki, bloków, uchwytów, Undo i naprawy zgłoszonej awarii poboczy nie potwierdzono natywnie w CAD. Szczegóły i ograniczenia: ZMIANY-AKTUALNE.md.

## Publikowanie
Dodanie numerowanego ZKDrogi-Setup-NUMER.exe do main uruchamia workflow, który sprawdza ProductVersion, tworzy SHA-256 i publikuje stabilne wydanie jako Latest. Numeracja: 0.30, 0.31 itd. Nie zmieniaj samej nazwy starego EXE.

