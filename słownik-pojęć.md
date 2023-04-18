# Słownik pojęć dla projektu MLOps
*stan na: 18.04.2023*

Po pierwsze, należy wyróżnić dwa kluczowe pojęcia w kontekście projektu MLOps, czyli:
- **Tworzenie (tracking)** - w ramach tworzenia rozumiemy cały proces tworzenia modeli uczenia maszynowego, od ich budowy, poprzez trenowanie, aż do ewaluacji. 
  Wspomagamy proces tworzenia poprzez możliwość zapisywania na naszej stronie najważniejszych informacji o modelu, takich jak:
  nazwa modelu, zbiór danych, parametry, wyniki na zbiorze testowym itp.
- **Monitorowanie (monitoring)** - w ramach monitorowania rozumiemy proces wdrażania modeli, czyli proces, w którym model jest wdrożony w środowisku produkcyjnym. 
  Wspomagamy proces monitorowania poprzez możliwość zapisywania predykcji oraz danych wejściowych modelu produkcyjnego, a także możliwość
  konfiguracji alertów mailowych dotyczących predykcji.

Dodatkowo, ważnym elementem naszego projektu jest **biblioteka** w języku Python, która umożliwia wygodne korzystanie z naszej strony.
Będzie ona zapewniać możliwość logowania danych w ramach **tworzenia** oraz **monitorowania** bezpośrednio z poziomu kodu w Pythonie.

## Tworzenie
Najważniejsze pojęcia związane z tworzeniem modeli:
- **Projekt** - projekt to po prostu pojedynczny projekt uczenia maszynowego, który może zawierać wiele eksperymentów 
  oraz modeli uruchamianych w ramach iteracji.
- **Eskperyment** - eksperyment to pojedynczy eksperyment, który może zawierać wiele iteracji.
- **Iteracja** - iteracja to pojedyncza iteracja, która zawiera konkretne informacje dla pojedynczego uruchomienia modelu.

Jako przykład eksperymentu możemy wyróżnić np. `Metody skalowania danych`, w ramach którego możemy mieć wiele iteracji, 
  np. `MinMaxScaler`, `StandardScaler`, `RobustScaler`.

- **Dataset** - dataset to zbiór danych, który jest wykorzystywany w ramach konkretnej iteracji.
  Nie będziemy przechowywać datasetów samych w sobie, a raczej odnośniki do nich, np. w postaci adresu URL lub ścieżki lokalnej.
- **Alerty** - w ramach alertów przy procesie tworzenia użytkownik będzie mógł skonfigurować,
  aby po udanym dodaniu iteracji na stronę otrzymywał on maila z informacją zwrotną zawierającą wyniki iteracji.
- **Wykresy** - interaktywne wykresy wizualizujące np. krzywą uczenia lub wyniki metryk na zbiorze testowym.

## Monitorowanie
Najważniejsze pojęcia związane z monitorowaniem modeli:
- **Model produkcyjny** - pojedynczy model, który jest wdrażany w środowisku produkcyjnym. Docelowo może być wybrany
  za pomocą kliknięcia w zakładce **Tworzenia** lub dodany ręcznie uploadując plik o rozszerzeniu .pkl.
- **Alerty** - w ramacha alertów dla monitorowania chcemy wyróżnić np. alerty dotyczące informowania o niepowodzeniu predykcji lub
alerty związane z wartością predykcji, np. gdy predykcja jest większa niż ustalona wartość.
- **Wykresy** - tworzenie wykresów w oparciu o dane produkcyjne oraz predykcje, np. w celu poszukiwania potencjalnego data shiftu.