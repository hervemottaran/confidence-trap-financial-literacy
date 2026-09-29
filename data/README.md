# Source data

The project uses the **2023 adult wave of IACOFI**, the Bank of Italy's survey of financial literacy and digital financial skills in Italy. The analysis uses 4,862 respondents aged 18–79.

## Download

1. Open the [Bank of Italy's official survey page](https://www.bancaditalia.it/statistiche/tematiche/indagini-famiglie-imprese/alfabetizzazione/index.html?com.dotmarketing.htmlpage.language=1).
2. Under **2023 Survey**, select **Database - STATA** in the English version of the page.
3. Extract the ZIP archive and locate `Database_ENG.dta`.
4. Keep the original filename and file bytes. Do not open and re-save the source file in another statistical application.

Official links:

- [2023 English Stata archive](https://www.bancaditalia.it/statistiche/tematiche/indagini-famiglie-imprese/alfabetizzazione/Database_STATA_EN.zip?language_id=1)
- [2023 data description and questionnaire](https://www.bancaditalia.it/statistiche/tematiche/indagini-famiglie-imprese/alfabetizzazione/Data-description-2023.pdf?language_id=1)

## Expected location

| Environment | Location of `Database_ENG.dta` |
|---|---|
| Local Jupyter | `data/raw/Database_ENG.dta`, relative to the repository root |
| Google Colab | `My Drive/The_Confidence_Trap/data/raw/Database_ENG.dta` in your own Google Drive |

Create the `raw` folder when placing the file. Other generated directories are created by the notebook.

## Registered input

| Check | Expected value |
|---|---|
| Filename | `Database_ENG.dta` |
| Size | 1,365,604 bytes |
| Rows | 4,862 |
| Columns | 219 |
| SHA-256 | `aded6652c0e6e200bd1b31090096c5a5d082f916a5dc8a666fe0e4ced71c583a` |

The notebook checks the original file checksum and dimensions before analysis. If the publisher changes the file and the checksum differs, investigate the version difference rather than removing the check.

## Availability

The Bank of Italy distributes the anonymised data for research purposes and states the conditions of use on its website. Download them from the original source and consult those conditions. This repository does not redistribute the raw dataset or respondent-level analytical checkpoints.

The notebook retains aggregate outputs so its methods and results can be inspected without access to the microdata.
