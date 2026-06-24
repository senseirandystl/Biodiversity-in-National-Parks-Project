# Biodiversity in National Parks

**End-to-end data analysis project** using Python to clean, explore, visualize, and statistically analyze National Park Service data on endangered and protected species.

## Project Overview

This project interprets data from the National Park Service on the conservation status of species across four major U.S. National Parks (Great Smoky Mountains, Yosemite, Bryce, and Yellowstone). The goals were to:

- Clean and prepare the data
- Explore patterns in conservation status by species category
- Visualize protected vs. non-protected species
- Use statistical testing to determine whether protection rates differ significantly between categories
- Investigate observations of a particularly prevalent species group (bats) across parks

**Data Sources** (provided via Codecademy):
- `species_info.csv` — 5,824 records with scientific name, common names, category (Mammal, Bird, Reptile, Amphibian, Fish, Vascular Plant, Nonvascular Plant), and conservation status
- `observations.csv` — 23,296 records of species observations with counts across the four parks

## Key Questions Addressed

- What is the distribution of conservation statuses across species?
- Are certain categories of species more likely to be protected or endangered?
- Are differences in protection rates between categories statistically significant?
- Which species (or type of species) has the highest number of observations, and how are those observations distributed across parks?

## Methodology

1. **Data Loading & Cleaning** — Loaded both CSVs with pandas; handled missing values in `conservation_status` by filling with "No Intervention".
2. **Exploratory Data Analysis** — Examined unique species (5,541), categories (7), parks (4), and observation totals.
3. **Visualization** — Created stacked bar chart of species by conservation status and category; later created grouped bar chart of bat observations by park.
4. **Feature Engineering** — Created `is_protected` flag and used regex/string matching on common names to identify bat species.
5. **Statistical Analysis** — Performed chi-square tests of independence on 2x2 contingency tables comparing protection rates between categories.
6. **Insight Generation** — Interpreted results and summarized findings.

## Key Findings

- **5,633 species** required "No Intervention"; only **191 species** had a protected status (Endangered: 16, Threatened: 10, Species of Concern: 161, In Recovery: 4).
- **Mammals (~17%)** and **Birds (~15%)** had the highest proportions of protected species. Reptiles, amphibians, and plants had lower rates.
- Chi-square tests showed **no statistically significant difference** in protection rates between mammals and birds, but a **statistically significant difference** between mammals and reptiles.
- Word-frequency analysis of mammal common names revealed "bat" as a highly frequent term. Follow-up analysis showed bats had the highest observation counts overall, with the largest numbers recorded in **Yellowstone National Park**.

## Visualizations

- Stacked bar chart showing number of species by conservation status and taxonomic category.
- Grouped bar chart comparing bat observations across the four national parks (protected vs. non-protected).

GitHub renders the full notebook with outputs and plots.

## Skills Demonstrated

This project showcases core data analyst competencies:

- **Python & pandas** — Data ingestion, cleaning (missing values, text processing), grouping/aggregation, pivoting, merging, feature engineering, and string/regex operations.
- **Data Visualization** — matplotlib and seaborn for clear, publication-ready bar charts and stacked visualizations.
- **Statistical Analysis** — Chi-square contingency tests for categorical data hypothesis testing.
- **Exploratory Data Analysis & Storytelling** — Posed meaningful business questions, interpreted statistical output, and communicated findings in context.
- **Reproducible Workflows** — Structured notebook with relative file paths and documented steps.

These skills directly transfer to roles involving data cleaning, dashboarding, A/B or categorical testing, and turning raw data into actionable conservation or operational insights.

## How to Run

```bash
git clone https://github.com/senseirandystl/Biodiversity-in-National-Parks-Project.git
cd Biodiversity-in-National-Parks-Project
pip install -r requirements.txt
jupyter notebook biodiversity.ipynb