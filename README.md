# NBA-stats-comparatives-W-RShiny

NBA stats comparative graphs with RShiny. This will allow the user to select players, seasons and different combinations of variables to analyze NBA performance.

## Folder structure

```
NBA-stats-comparatives-W-RShiny/
├── NBA_App.Rmd        Step 1: cleans the raw data
├── UI/
│   └── UI.Rmd         Step 2: the Shiny app
├── input-data/        Raw CSV files (read by NBA_App.Rmd)
└── output-data/       Cleaned CSV files (written by NBA_App.Rmd, read by UI.Rmd)
```

### input-data/

The raw statistics. `NBA_App.Rmd` only reads these files and never changes them.

- `nba_season15.16.csv` to `nba_season23.24.csv`: one shooting-by-distance table for each season from 2015-2016 to 2023-2024.
- `nbatable.csv`: the same kind of table for the 2024-2025 season.
- `nba_totals.csv`: player statistic totals (points, rebounds, assists, and so on) for the 2024-2025 season.

### output-data/

This is where the output goes. Running `NBA_App.Rmd` creates three cleaned files here, and `UI.Rmd` reads them to draw the charts:

| File | Used for |
| --- | --- |
| `chart1and2_data.csv` | Field Goal Attempts and Shooting Accuracy charts |
| `chart3_data.csv` | Season Totals chart |
| `chart4_data.csv` | Player Progression chart |

These files are created every time `NBA_App.Rmd` runs, so they are not stored in the repository. The folder is empty until you run it.

## Instructions

1. Download the whole project and keep the folders as they are.
2. Install the R packages the files use: `dplyr`, `ggplot2`, `scales`, `shiny`, `tidyr`, `plotly` and `RColorBrewer`.
3. Open **NBA_App.Rmd** in RStudio and run it. It reads `input-data/` and writes the cleaned files into `output-data/`.
4. Open **UI/UI.Rmd** and run it to show the app. It reads the files in `output-data/`.

RStudio runs each `.Rmd` file from the folder it is in, so you do not need to set a working directory. If you run the code from the console instead, set the working directory to the main project folder (for `NBA_App.Rmd`) or to the `UI` folder (for `UI.Rmd`).

If `UI.Rmd` says the chart files are missing, run `NBA_App.Rmd` first.

Please email **nickymoreno1110@gmail.com** if you encounter any issues.

Enjoy the App!
