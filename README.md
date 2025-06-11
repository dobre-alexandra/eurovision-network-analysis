# Eurovision Voting Network Analysis

## Overview

This project explores the voting patterns within the Eurovision Song Contest using social network analysis and community detection techniques.

 By constructing and analyzing networks of historical public and jury votes, the project aims to uncover geographical, cultural, and strategic alliances that influence voting behaviors, providing insights into the socio-cultural dynamics at play.

## Key Features & Analysis

* **Network Construction:** Built directed voting networks for:
    * 2018-2023 Public Votes (`net_5pub`)
    * 2018-2023 Jury Votes (`net_5jury`)
    * 1957-2023 Historical Jury Votes (`net_alljury`)
    Nodes represent countries, and edges represent vote exchanges, weighted by vote counts or sums.
* **Network Visualization:** Implemented geospatial plotting of networks with nodes positioned by capital city latitude/longitude. Visualizations are enhanced by:
    * Sizing nodes by **in-strength centrality** (received votes).
    * Coloring nodes by their **geographical region**.
    * Sizing edges by vote weight, allowing for clear visual interpretation of voting intensity.
* **Quantitative Network Measures:** Calculated and compared key network characteristics for public and jury voting in 2018-2023:
    * **Reciprocity:** Measuring mutual vote exchanges.
    * **Global Transitivity:** Assessing the clustering tendency of voting relationships.
    * **Assortativity by Region:** Quantifying the preference for within-region voting.
* **Community Detection:** Applied the **Spinglass community detection algorithm** to the long-term 1957-2023 jury network to identify hidden voting blocs and alliances, weighted by total jury points.
* **Interpretive Analysis:** Discussed findings, comparing algorithmic communities with geographical regions, and exploring how cultural ties, historical alliances, and other factors might explain observed voting patterns beyond mere proximity.

## Data

The analysis utilizes a collection of CSV datasets provided by the course convener, primarily sourced from Eurovision live broadcasts and fan sites:

* `euro_public_count_18-23.csv`: Top public vote counts (2018-2023).
* `euro_jury_count_18-23.csv`: Top jury vote counts (2018-2023).
* `euro_sum_jury_points.csv`: Sum of all jury points awarded (1957-2023).
* `meta_eurovision.csv`: Metadata for participating countries, including geographical region, GDP per capita, population, area, and capital city coordinates.

## Tools & Technologies

* **R:** Primary language for data loading, network construction, analysis, and visualization.
    * `igraph`: Core package for social network analysis, network manipulation, and visualization.
    * `knitr`: For dynamic report generation and creating markdown tables.
    * `dplyr` & `tibble`: For data manipulation and structuring results.
    * `scales`: For scaling network attributes (e.g., node sizes, edge widths).
    * `RColorBrewer`: For generating color palettes for visualizations.
* **RStudio:** Integrated Development Environment (IDE) for R.
* **GitHub:** Version control and hosting of the project code and rendered analysis.

## How to View This Project

This project's analysis and results are presented in an R Markdown document, which has been rendered to a GitHub-friendly Markdown file (`.md`). To view the full analysis directly on GitHub, including all plots and tables:

1.  Navigate to the `eurovision-network-analysis.Rmd` file in this repository.
2.  Click on the rendered `.md` file (e.g., `eurovision-network-analysis.md`) that is generated from the `.Rmd` when it's pushed to GitHub. This file should display the complete report, including embedded images and tables, directly in your browser within the GitHub interface.

## Repository Structure

* `eurovision-network-analysis.Rmd`: The R Markdown source file containing all code and narrative.
* `eurovision-network-analysis.md`: The rendered Markdown output file, viewable directly on GitHub.

## Acknowledgements

Special thanks to the course convener for MY461: Social Network Analysis at the London School of Economics (LSE) for compiling and providing the datasets used in this project.