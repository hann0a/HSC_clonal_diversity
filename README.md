# HSC clonal diversity

Analiza związku fenotypu powierzchniowego pojedynczych hematopoetycznych komórek macierzystych z różnorodnością klonalną powstających z nich kolonii, łącząca dane z sortowania indeksowego (*ang. index sorting*) z testem klonalnym o odczycie cytometrycznym (CFU-FACS).

## Kontekst

Kod analityczny do pracy licencjackiej na kierunku bioinformatyka (Wydział Biochemii, Biofizyki i Biotechnologii, Uniwersytet Jagielloński). Dane pochodzą z badań realizowanych w ramach grantu ERC StemMemo (*„What does your blood remember? The memory of hematopoietic stem cells"*, ID: 101041737).

## Struktura repozytorium

```         
├── analiza/
│   ├── exp_rsm_analiza.qmd      # analiza głównego eksperymentu (n=623)
│   ├── exp_9_analiza.qmd        # analiza exp_9 (n=173)
│   ├── exp_mat_analiza.qmd      # analiza exp_mat (n=187)
│   ├── analiza_dbrda.qmd        # db-RDA dla wszystkich eksperymentów
│   └── dane/                    # dane wejściowe (patrz: Dostępność danych)
├── wyniki/                      # ryciny i tabele generowane przez .qmd
└── README.md
```

## Zakres analizy

-   wskaźniki różnorodności alpha: Richness, Shannon, Simpson, Evenness (pakiet `vegan`)
-   niepodobieństwo Bray-Curtis jako miara różnorodności beta
-   analiza jednoczynnikowa: uogólnione modele liniowe (GLM) z doborem rozkładu do charakteru wskaźnika (Poisson / regresja beta / model liniowy), z korektą Benjaminiego-Hochberga w obrębie każdego wskaźnika
-   analiza wieloczynnikowa: analiza redundancji oparta na odległościach (db-RDA), z testami permutacyjnymi modelu globalnego i testami marginalnymi markerów
-   wizualizacja: ordynacja PCoA macierzy Bray-Curtis z wektorami populacji (`envfit`)

## Wymagania

-   R (≥ 4.0)
-   [Quarto](https://quarto.org/)
-   pakiety R: `vegan`, `betareg`, `ggplot2`, `dplyr`, `tidyr`, `tibble`, `moments`, `patchwork`, `ggrepel`, `readxl`

Instalacja pakietów:

``` r
install.packages(c("vegan", "betareg", "ggplot2", "dplyr", "tidyr",
                   "tibble", "moments", "patchwork", "ggrepel", "readxl"))
```

## Autorka

Hanna Milnikel — praca licencjacka, 2026

Promotor: dr hab. Agnieszka Jaźwa-Kusior

Opiekun: dr Krzysztof Szade.
