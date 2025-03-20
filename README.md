# library_comparisons
Comparisons of libraries in Louisville
I downloaded the Louisville Public Library Collection data on 12/18/2024 from https://data.louisvilleky.gov/
I also downloaded the age demographic information for all the zipcodes in Jefferson County from https://data.census.gov/
The goal is to see whether the collections in the libraries match the age demographics of the community that surrounds each library.

In a second notebook (and Tableau dashboard), I used the library collection data in comparison with education level data from the Census Bureau. 
The education levels for each zipcode are compared with the publication dates for the adult collection in each library (binned into decades).

The Tableau visualization can be found here: https://public.tableau.com/views/mapviz_17424942099340/Age?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link
*** For the maps, the library pie chart will update when a library location is clicked on. The zipcode data will update just by hovering over it with the cursor.



Installing virtual environment and the Matplotlib and Pandas packages (this was performed in VS Code):
PS C:\Users\Nick Campbell\Desktop\code_you_project\library_comparisons> python -m venv venv
PS C:\Users\Nick Campbell\Desktop\code_you_project\library_comparisons> pip install pandas
Collecting pandas
  Using cached pandas-2.2.3-cp311-cp311-win_amd64.whl.metadata (19 kB)
Collecting numpy>=1.23.2 (from pandas)
  Downloading numpy-2.2.3-cp311-cp311-win_amd64.whl.metadata (60 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 60.8/60.8 kB 270.6 kB/s eta 0:00:00
Requirement already satisfied: python-dateutil>=2.8.2 in c:\users\nick campbell\desktop\code_you_project\library_comparisons\venv\lib\site-packages (from pandas) (2.9.0.post0)
Collecting pytz>=2020.1 (from pandas)
  Downloading pytz-2025.1-py2.py3-none-any.whl.metadata (22 kB)
Collecting tzdata>=2022.7 (from pandas)
  Downloading tzdata-2025.1-py2.py3-none-any.whl.metadata (1.4 kB)
Requirement already satisfied: six>=1.5 in c:\users\nick campbell\desktop\code_you_project\library_comparisons\venv\lib\site-packages (from python-dateutil>=2.8.2->pandas) (1.17.0)
Downloading numpy-2.2.3-cp311-cp311-win_amd64.whl (12.9 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 12.9/12.9 MB 5.5 MB/s eta 0:00:00
Downloading pytz-2025.1-py2.py3-none-any.whl (507 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 507.9/507.9 kB 4.0 MB/s eta 0:00:00
Downloading tzdata-2025.1-py2.py3-none-any.whl (346 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 346.8/346.8 kB 1.3 MB/s eta 0:00:00
Installing collected packages: pytz, tzdata, numpy, pandas
Successfully installed numpy-2.2.3 pandas-2.2.3 pytz-2025.1 tzdata-2025.1
PS C:\Users\Nick Campbell\Desktop\code_you_project\library_comparisons> pip install matplotlib
Collecting matplotlib
  Downloading matplotlib-3.10.0-cp311-cp311-win_amd64.whl.metadata (11 kB)
Collecting contourpy>=1.0.1 (from matplotlib)
  Using cached contourpy-1.3.1-cp311-cp311-win_amd64.whl.metadata (5.4 kB)
Collecting cycler>=0.10 (from matplotlib)
  Using cached cycler-0.12.1-py3-none-any.whl.metadata (3.8 kB)
Collecting fonttools>=4.22.0 (from matplotlib)
  Downloading fonttools-4.56.0-cp311-cp311-win_amd64.whl.metadata (103 kB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 104.0/104.0 kB 669.4 kB/s eta 0:00:00
Collecting kiwisolver>=1.3.1 (from matplotlib)
  Downloading kiwisolver-1.4.8-cp311-cp311-win_amd64.whl.metadata (6.3 kB)
Requirement already satisfied: numpy>=1.23 in c:\users\nick campbell\desktop\code_you_project\library_comparisons\venv\lib\site-packages (from matplotlib) (2.2.3)
Requirement already satisfied: packaging>=20.0 in c:\users\nick campbell\desktop\code_you_project\library_comparisons\venv\lib\site-packages (from matplotlib) (24.2)
Collecting pillow>=8 (from matplotlib)
  Downloading pillow-11.1.0-cp311-cp311-win_amd64.whl.metadata (9.3 kB)
Collecting pyparsing>=2.3.1 (from matplotlib)
  Downloading pyparsing-3.2.1-py3-none-any.whl.metadata (5.0 kB)
Requirement already satisfied: python-dateutil>=2.7 in c:\users\nick campbell\desktop\code_you_project\library_comparisons\venv\lib\site-packages 
(from matplotlib) (2.9.0.post0)
Requirement already satisfied: six>=1.5 in c:\users\nick campbell\desktop\code_you_project\library_comparisons\venv\lib\site-packages (from python-dateutil>=2.7->matplotlib) (1.17.0)
Downloading matplotlib-3.10.0-cp311-cp311-win_amd64.whl (8.0 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 8.0/8.0 MB 5.0 MB/s eta 0:00:00
Using cached contourpy-1.3.1-cp311-cp311-win_amd64.whl (219 kB)
Using cached cycler-0.12.1-py3-none-any.whl (8.3 kB)
Downloading fonttools-4.56.0-cp311-cp311-win_amd64.whl (2.2 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.2/2.2 MB 4.8 MB/s eta 0:00:00
Downloading kiwisolver-1.4.8-cp311-cp311-win_amd64.whl (71 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 72.0/72.0 kB 791.4 kB/s eta 0:00:00
Downloading pillow-11.1.0-cp311-cp311-win_amd64.whl (2.6 MB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 2.6/2.6 MB 5.2 MB/s eta 0:00:00
Downloading pyparsing-3.2.1-py3-none-any.whl (107 kB)
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 107.7/107.7 kB 1.2 MB/s eta 0:00:00
Installing collected packages: pyparsing, pillow, kiwisolver, fonttools, cycler, contourpy, matplotlib
Successfully installed contourpy-1.3.1 cycler-0.12.1 fonttools-4.56.0 kiwisolver-1.4.8 matplotlib-3.10.0 pillow-11.1.0 pyparsing-3.2.1
