# Data preparation

Source: Bank of England nominal government liability curves.
Workbook used: GLC Nominal daily data_2016 to 2024.xlsx.

Sheets:
- 4. spot curve: maturities expressed in years.
- 3. spot, short end: maturities expressed in months;
  divide by 12 to convert to years.

Cleaning:
1. Preserve the original workbook.
2. Remove rows with no observed rates.
3. Preserve partially missing observations in the cleaned data.
4. Convert quoted percentages to decimals by dividing by 100.
5. Reshape to one row per date and maturity.
6. Verify overlapping rates before removing duplicate
   date/maturity observations.
7. Export observed rates as nominal_spot_observed.csv.

Required CSV columns:
- date: day-month-year
- tenor_year: maturity in years
- spot_rate_decimal: continuously compounded annual rate

The notebook selects 2-, 5-, 10-, 20- and 30-year maturities,
calculates aligned yield changes in basis points, and retains
only intervals with all five changes available.

Missing rates are not replaced with zero or forward-filled.
Each historical interval is an independent stress scenario.
