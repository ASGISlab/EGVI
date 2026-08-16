# Enhanced GVI Quantification


## Contents

```
.
├── README.md              # This file
├── data_dictionary.csv    # Column-level definitions for every CSV in data/
└── data/
    ├── kh_houseprice_low.csv
    ├── kh_houseprice_mid.csv
    ├── kh_houseprice_high.csv
    ├── tp_houseprice_low.csv
    ├── tp_houseprice_mid.csv
    └── tp_houseprice_high.csv
```

Each city's transactions are split into three files — `low`, `mid`, and
`high` — by **transaction price tertile** (`low` = bottom third, `mid` =
middle third, `high` = top third of `Y` for that city). All six files share
the same 14 columns.

| File | Rows | `Y` range (min–max) | `Y` mean |
|---|---:|---:|---:|
| `kh_houseprice_low.csv`  | 32,133 | 229 – 49,346 | 38,170 |
| `kh_houseprice_mid.csv`  | 64,264 | 49,347 – 85,406 | 66,430 |
| `kh_houseprice_high.csv` | 32,133 | 85,407 – 2,324,577 | 112,883 |
| `tp_houseprice_low.csv`  | 29,950 | 714 – 152,869 | 118,128 |
| `tp_houseprice_mid.csv`  | 59,895 | 152,872 – 248,204 | 197,704 |
| `tp_houseprice_high.csv` | 29,948 | 248,207 – 3,721,850 | 321,409 |


## Data dictionary

The authoritative column definitions live in
[`data_dictionary.csv`](./data_dictionary.csv); the table below is a
convenience copy.

| Variable | Description | Type | Unit | Coding |
|---|---|---|---|---|
| `Y` | Variable included in the housing transaction dataset (target/response variable — please confirm exact definition and unit) | Numeric | — | — |
| `Enhanced_GVI_quantification` | Quantitative measure related to the Enhanced Green View Index (Enhanced GVI) | Numeric | — | — |
| `Transaction_including_the_first_floor_versus_not` | Whether the transaction property includes the first floor | Numeric | — | 0 = No, 1 = Yes |
| `Housing_age` | Age of the housing property | Numeric | Years | — |
| `Transaction_year` | Transaction year (ROC calendar year) | Numeric | ROC year | — |
| `Condominium_versus_not` | Whether the property is a condominium | Numeric | — | 0 = No, 1 = Yes |
| `Apartment_versus_not` | Whether the property is an apartment | Numeric | — | 0 = No, 1 = Yes |
| `Studio_versus_not` | Whether the property is a studio | Numeric | — | 0 = No, 1 = Yes |
| `Detached_House_versus_not` | Whether the property is a detached house | Numeric | — | 0 = No, 1 = Yes |
| `Storefront_versus_not` | Whether the property has a storefront | Numeric | — | 0 = No, 1 = Yes |
| `Commercial_building_versus_not` | Whether the property is a commercial building | Numeric | — | 0 = No, 1 = Yes |
| `mrt_d` | Distance to the nearest MRT station | Numeric | m | — |
| `school_d` | Distance to the nearest school | Numeric | m | — |
| `park_d` | Distance to the nearest park | Numeric | m | — |

**Note:** `Transaction_year` is given in the ROC (Republic of China)
calendar — add 1911 to convert to the Gregorian year (e.g., `108` → 2019).
