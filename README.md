# Amazon Purchases Analytics | Power BI

**Samodzielny projekt portfolio z zakresu analizy danych i Business Intelligence**  
**Autorka:** Alona Shemetilo  
**Narzędzia:** Power BI Desktop · Power Query · DAX · Modelowanie danych

> **Status:** raport przygotowany; publikacja interaktywnej wersji i repozytorium — w planie. Linki zostaną uzupełnione po publikacji.

## O projekcie

**Amazon Purchases Analytics** to interaktywny raport Power BI oparty na udostępnionym zbiorze historii zakupów na Amazonie w USA z lat **2018–2022**. Projekt obejmuje **1 810 793 rekordy zakupowe**.

Celem było przeanalizowanie zmian wartości zakupów w czasie, struktury kategorii oraz najczęściej występujących produktów, a także przedstawienie wyników w czytelnym raporcie umożliwiającym samodzielną eksplorację danych.

**Ważne:** zbiór zawiera historie zakupowe uczestników badania. Nie jest reprezentatywną próbą całej sprzedaży Amazon i nie służy do szacowania wyników finansowych firmy.

## Pytania analityczne

- Jak zmieniały się wartość i liczba rekordów zakupowych w latach 2018–2022?
- Jak kształtowała się średnia wartość rekordu zakupowego?
- Które kategorie i produkty wyróżniały się pod względem wartości oraz częstości występowania?
- Jak zmieniały się wybrane kategorie w kolejnych latach?
- Jak zaprezentować wyniki w sposób umożliwiający filtrowanie i porównywanie danych?

## Najważniejsze wskaźniki

| KPI | Wynik dla analizowanego zbioru |
| --- | ---: |
| Purchase Records | 1 810 793 |
| Total Purchase Value | 43 125 630 USD |
| Average Value per Purchase Record | 23,82 USD |
| Total Units Purchased | 1 971 309 |

Wskaźnik **Purchase Records** odnosi się do rekordów danych, a nie do liczby unikalnych zamówień lub klientów.

## Wybrane wnioski

- Wartość zakupów w analizowanym zbiorze wzrosła z około **5,5 mln USD w 2018 r.** do około **10,7 mln USD w 2022 r.**
- Kategoria **PET_FOOD** odnotowała wzrost wartości zakupów o **158,6%** w latach 2018–2022. W tym samym okresie liczba rekordów tej kategorii wzrosła o **139,1%**.
- Analiza produktów pozwoliła wskazać często występujące pozycje, w tym **GIFT CARD RELOAD**, **AMAZON EGIFT CARD** i **AMAZON RELOAD**.

Wnioski dotyczą wyłącznie analizowanego zbioru i nie powinny być uogólniane na wszystkich klientów Amazon.

## Zakres wykonanej pracy

1. **Power Query:** przygotowanie danych oraz kontrole brakujących wartości, duplikatów i jakości wybranych pól.
2. **Model danych:** opracowanie tabeli kalendarza `DimDate` i relacji z tabelą faktów `amazon-purchases`.
3. **DAX:** przygotowanie miar KPI oraz kolumn obliczeniowych potrzebnych do analizy i prezentacji danych.
4. **Raport:** zaprojektowanie interaktywnych stron analizujących trendy, kategorie i produkty.
5. **Walidacja:** kontrola wyników, działania filtrów i wybranych aspektów wydajności.
6. **Dokumentacja:** opisanie metod, decyzji projektowych, ograniczeń i testów.

## Model danych

Główna tabela faktów: `amazon-purchases`  
Tabela dat: `DimDate`  
Relacja: `DimDate[Date]` **(1)** → `amazon-purchases[Order Date]` **(*)**

Dodatkowe tabele pomocnicze w modelu: `Check_Rows_By_Year` (kontrola danych) oraz `Measures Table` (organizacja miar).

## Strony raportu

| Strona | Przeznaczenie |
| --- | --- |
| `LP` | Strona startowa i nawigacja |
| `Purchase Overview` | Główne KPI i analiza zakupów w czasie |
| `Category Analysis` | Analiza kategorii produktów |
| `Product Analysis` | Analiza wybranych produktów |
| `Conclusions` | Podsumowanie obserwacji i ograniczeń |

W pliku znajduje się również ukryta strona techniczna `Data Validation`, wykorzystywana do kontroli danych.

## Podgląd raportu

### Strona główna (LP)
![Strona główna raportu Amazon Purchases Analytics](images/home.png)

### Purchase Overview
![Purchase Overview](images/purchase-overview.png)

### Category Analysis
![Category Analysis](images/category-analysis.png)

### Product Analysis
![Product Analysis](images/product-analysis.png)

### Conclusions
![Conclusions](images/conclusions.png)

<!-- Po dodaniu obrazów można odkomentować poniższe odnośniki:
![Purchase Overview](images/purchase-overview.png)
![Category Analysis](images/category-analysis.png)
![Product Analysis](images/product-analysis.png)
![Conclusions](images/conclusions.png)
-->

## Materiały projektu

- **Raport interaktywny (Power BI):** [LINK DO UZUPEŁNIENIA PO PUBLIKACJI]
- **Plik PBIX:** `report/Alona_Shemetilo_Amazon_Purchases_Analytics.pbix` — do dodania po sprawdzeniu rozmiaru i zawartości pliku.
- **Dokumentacja techniczna (PDF):** `documentation/Dokumentacja_techniczna.pdf` — do dodania.

## Źródło danych i ograniczenia

**Źródło:** Berke i in. (2023), *Open e-commerce 1.0: Five years of crowdsourced U.S. Amazon purchase histories with user demographics*, Harvard Dataverse.  
**DOI:** `10.7910/DVN/YGLYDY`  
**Deklarowana licencja zbioru:** CC0 (należy zachować informację o źródle i zweryfikować warunki konkretnych plików przed ich ewentualnym udostępnieniem).

Ograniczenia interpretacji:

- Dane pochodzą od uczestników badania, a nie z pełnej bazy transakcyjnej Amazon.
- Brakujące nazwy produktów i kategorii mogą wpływać na zakres analiz szczegółowych.
- `Unknown Category` oznacza brak informacji o kategorii, a nie odrębną kategorię biznesową.
- Wyniki mają charakter opisowy; nie dowodzą związków przyczynowo-skutkowych.

## Autorka

**Alona Shemetilo**  
Portfolio: **Data Analytics / Business Intelligence**  
Obszary rozwoju: **Power BI, SQL, Excel**  

*Projekt wykonany samodzielnie jako element portfolio analitycznego. Nie jest realizacją na zlecenie Amazon.*
