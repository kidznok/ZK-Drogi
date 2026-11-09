# ZK Drogi 0.43 — kompaktowe okno geometrii i wymiarowanie poszerzeń

## Geometria osi
- Ciemne, kompaktowe, pływające okno zgodne z zaakceptowanym układem: nagłówek PI i kilometraż osi, strzałki poprzedni/następny PI, Wskaż, wybór układu, pola R/L₁/L₂ w jednym rzędzie.
- Podgląd z siatką i legendą: prosta czerwona, łuk żółty, klotoidy pomarańczowe. Pod nim Δ i T₁/T₂ oraz rozwijane parametry wynikowe. Etykiety punktów mają ograniczanie kolizji.
- Stała dolna belka Cofnij zmiany / Zastosuj. W razie zmniejszenia okna przewija się zawartość, a przyciski pozostają dostępne. Okno przenosi się za nagłówek i zamyka krzyżykiem.
- Zachowane niezależne długości klotoid, walidacja geometrii i aktualizacja zależnego planu w transakcji. Po zapisie kilometraż PI jest odczytywany ponownie. 3D i skarpy przeliczane osobno.

## Poszerzenia na planie
- W zakresie automatycznego poszerzenia rysowana jest przerywana krawędź nominalna, bez automatycznego przyrostu szerokości; zapisane korekty ręczne pozostają w szerokości nominalnej. Linia występuje po stronie poszerzenia i ma ciągły wzór kreskowy przez kolejne wierzchołki.
- Na początku wprowadzenia poszerzenia: ciąg wymiarów obu pasów nominalnych. Na początku łuku z pełnym poszerzeniem: pas | pas | poszerzenie. Symetrycznie na końcu łuku i wyprowadzenia poszerzenia.
- Są to natywne wymiary CAD na jednej wspólnej linii prostopadłej do osi, bez odnośnika dla poszerzenia. Nie rysuje się zerowego dodatkowego wymiaru. Dla przeciwnego zwrotu łuku łańcuch jest lustrzany.
- Dodatkowy wymiar pokazuje łączny przyrost szerokości jezdni po stronie wewnętrznej według obecnego modelu WR-D (nie ponowne dodanie poszerzenia każdego pasa). Nominalnym podziałem do tego łańcucha jest oś, nie przesunięta linia podziału ruchu.
- Oznaczenia zastępują wcześniejsze wymiary pary jezdni przy etykietach spadków, są indeksowane i odtwarzane bez kumulowania kopii przy aktualizacji planu. Reszta wymiarów elementów pozostaje. Widoczność powiązana z Pokaż wiązania. Krótsze zakresy elementów są respektowane.

Weryfikacja: 396 testów obliczeniowych; test rzeczywistego panelu WPF z układem pól w jednym rzędzie, nazwą i kilometrażem osi, widocznością dolnej belki, rozwijaniem parametrów, edycją R/L₁/L₂ i ochroną przed niepoprawną geometrią. Panel wyrenderowano i obejrzano. Testy aktualizatora oraz kompilacja z API BricsCAD V26. Wymiarów i nowego okna w natywnej sesji BricsCAD jeszcze nie zweryfikowano.

Zamknij wszystkie sesje BricsCAD przed instalacją wersji 0.43. Następnie Aktualizuj plan, aby odtworzyć oznaczenia poszerzeń, oraz Geometria osi, aby otworzyć nowe okno.
