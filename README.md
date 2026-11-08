# ZK Drogi
Wersja testowa nakładki do projektowania dróg w BricsCAD V26 x64. Instalatory: Releases.

## 0.40 — boczna paleta geometrii osi
- Geometria osi → kliknij okolice PI lub łuku → paleta boczna z podglądem.
- Osobne parametry R, L₁ i L₂. Załamanie, sam łuk, klotoida–łuk–klotoida. Klotoidy mogą mieć różne długości lub jedna z nich może mieć 0.
- Proste czerwone, łuk żółty, klotoidy pomarańczowe; wyniki Δ, T₁/T₂, długości, A₁/A₂ i L₁/R/L₂/R.
- Wskaż inny PI lub użyj nawigacji. Poprawny szkic parametrów pozostaje do Zastosuj. Pola nie przebudowują DWG; przy wpisywaniu sprawdzany jest wybrany PI i sąsiedzi.
- Zastosuj zapisuje oś i aktualizuje zależny plan w jednej transakcji. Kontrola kolizji krzywych, zmienionej osi i innego aktywnego DWG. 3D i skarpy pozostają ręczne.
- Stare dane z jedną długością L są odczytywane jako równe L₁=L₂. Opisy osi i granice poszerzeń uwzględniają długość wyjściową.

373 testy obliczeniowe, test rzeczywistego panelu WPF i 12 aktualizatora przechodzi. Panel wyrenderowano i obejrzano. Dokowania i zapisu wewnątrz natywnego BricsCAD jeszcze nie zweryfikowano. Szczegóły: ZMIANY-AKTUALNE.md.

Zamknij wszystkie sesje BricsCAD przed instalacją. Wymagany V26 x64 i .NET Desktop Runtime 8 z linii 8. Wersja: 0.40.
