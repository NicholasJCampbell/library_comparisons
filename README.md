# Library and Neighborhood Comparison

## Project Overview

This project utilizes demographic information from the Census Bureau and the Louisville Free Public Library Collection. The goal of the project is to evaluate whether the collection of each library matches the demographics of its respective neighborhood.
This is the capstone project for Code:Louisville and uses Python and Tableau.

### Conclusions/Summary
#### Age Comparisons
In general, the teen book collection is a much smaller percentage than the other books, this is true even in the areas with much larger teen demographics in the western and southern areas (cf. Portland, Iroquois, Shively, Southwest, South Central). This is the opposite of the children's collections. The percentage of children's books in the library collections are significantly higher than the percentage of the neighborhood population that are children at every branch except the Main branch. Though teens may not be the most engaged audience for library books, they are also developing reading skills and should have more books available to them.
#### Education and Recency Comparisons
Portland, Shawnee, and Fairdale have some of the lowest percentages of college graduates (and education levels in general) but fairly high percentages of books published in the past 5 years (same for books published between 2010-2019). So, the neighborhoods with higher education levels do not necessarily receive all the newest books (cf. Portland and St. Matthews/Eline or Northeast).

## Data Sources

- [The Louisville Public Library Collection](https://data.louisvilleky.gov/datasets/LOJIC::louisville-metro-ky-library-collection-inventory-/about) downloaded 12/18/2024 
- [Age Demographics by Zipcode](https://data.census.gov/) downloaded 12/18/2024
- [Library Spatial Data](https://data.louisvilleky.gov/datasets/LOJIC::louisville-ky-free-public-libraries-1/about) downloaded 12/18/2024
- [Zipcode Spatial Data](https://data.louisvilleky.gov/datasets/LOJIC::jefferson-county-ky-zip-codes/about) downloaded 12/18/2024
- [Education Demographics by Zipcode](https://data.census.gov/) downloaded 2/26/2025

---
## Project Outline
- **Data Exploration:** Jupyter notebooks in VS Code.
- **Analysis:** Python with the Pandas and Numpy packages for data cleaning.
- **Visualizations :** Initial visualizations using Matplotlib in Jupyter notebooks. 
- **Dashboard:** Created [Tableau Dashboard](https://public.tableau.com/views/mapviz_17424942099340/Age?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link).

---

## Getting Started

To run this project, follow these steps:

1. Clone the repository: `git clone https://github.com/NicholasJCampbell/library_comparisons.git`
2. Install the necessary dependencies: `pip install -r requirements.txt`
3. Explore the Jupyter notebooks or scripts in the respective folders.

###  Virtual Environment Instructions

1. After you have cloned the repo to your machine, navigate to the project 
folder in GitBash/Terminal.
1. Create a virtual environment in the project folder. 
1. Activate the virtual environment.
1. Install the required packages. 
1. When you are done working on your repo, deactivate the virtual environment.

Virtual Environment Commands

| Command | Linux/Mac | GitBash |
|---------|-----------|---------|
| Create | `python3 -m venv venv` | `python -m venv venv` |
| Activate | `source venv/bin/activate` | `source venv/Scripts/activate` |
| Install | `pip install -r requirements.txt` | `pip install -r requirements.txt` |
| Deactivate | `deactivate` | `deactivate` |

---

## Features Utilized for the project

  | Feature        | Description                           |
  |----------------|---------------------------------------|
  | Read TWO data files| Used 1 CSV file from Louisville Open Data, multiple (78 total) CSVs from the Census Bureau, 2 GeoJSONs from Louisville Open Data |
  | Clean your data and perform a pandas merge with your two data sets, then calculate some new values based on the new data set.      | Cleaned and merged data (two different ways) with Pandas and in Tableau. Calculated population percentages in both datasets. |
  | Make 3 Matplotlib visualizations | Made several bar plots for initial data interpretation. |
  | Make a Tableau dashboard  | Made two [Tableau dashboards](https://public.tableau.com/views/mapviz_17424942099340/Age?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link). |
  | Utilize a virtual environment | Made a virtual environment and included instructions in the ReadMe. |
  | Annotate your code with markdown cells in Jupyter Notebook | Included notes describing each code block and section descriptions in Markdown cells. |
