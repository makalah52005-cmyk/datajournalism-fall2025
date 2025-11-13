[assignment6.ipynb](https://github.com/user-attachments/files/23517269/assignment6.ipynb)
{
 "cells": [
  {
   "cell_type": "code",
   "execution_count": 1,
   "id": "73ea49c1-e182-4af3-ac86-6770a313fa0b",
   "metadata": {
    "collapsed": true,
    "jupyter": {
     "outputs_hidden": true,
     "source_hidden": true
    },
    "scrolled": true
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "Requirement already satisfied: datawrapper in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (2.0.13)\n",
      "Requirement already satisfied: importlib_metadata in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from datawrapper) (8.4.0)\n",
      "Requirement already satisfied: rich in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from datawrapper) (14.2.0)\n",
      "Requirement already satisfied: requests in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from datawrapper) (2.32.3)\n",
      "Requirement already satisfied: pandas in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from datawrapper) (2.2.2)\n",
      "Requirement already satisfied: pydantic in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from datawrapper) (2.12.4)\n",
      "Requirement already satisfied: ipython in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from datawrapper) (8.26.0)\n",
      "Requirement already satisfied: zipp>=0.5 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from importlib_metadata->datawrapper) (3.20.1)\n",
      "Requirement already satisfied: decorator in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from ipython->datawrapper) (5.1.1)\n",
      "Requirement already satisfied: jedi>=0.16 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from ipython->datawrapper) (0.19.1)\n",
      "Requirement already satisfied: matplotlib-inline in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from ipython->datawrapper) (0.1.7)\n",
      "Requirement already satisfied: prompt-toolkit<3.1.0,>=3.0.41 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from ipython->datawrapper) (3.0.47)\n",
      "Requirement already satisfied: pygments>=2.4.0 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from ipython->datawrapper) (2.18.0)\n",
      "Requirement already satisfied: stack-data in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from ipython->datawrapper) (0.6.2)\n",
      "Requirement already satisfied: traitlets>=5.13.0 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from ipython->datawrapper) (5.14.3)\n",
      "Requirement already satisfied: colorama in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from ipython->datawrapper) (0.4.6)\n",
      "Requirement already satisfied: numpy>=1.26.0 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from pandas->datawrapper) (2.1.0)\n",
      "Requirement already satisfied: python-dateutil>=2.8.2 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from pandas->datawrapper) (2.9.0)\n",
      "Requirement already satisfied: pytz>=2020.1 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from pandas->datawrapper) (2024.1)\n",
      "Requirement already satisfied: tzdata>=2022.7 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from pandas->datawrapper) (2024.1)\n",
      "Requirement already satisfied: annotated-types>=0.6.0 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from pydantic->datawrapper) (0.7.0)\n",
      "Requirement already satisfied: pydantic-core==2.41.5 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from pydantic->datawrapper) (2.41.5)\n",
      "Requirement already satisfied: typing-extensions>=4.14.1 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from pydantic->datawrapper) (4.15.0)\n",
      "Requirement already satisfied: typing-inspection>=0.4.2 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from pydantic->datawrapper) (0.4.2)\n",
      "Requirement already satisfied: charset-normalizer<4,>=2 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from requests->datawrapper) (3.3.2)\n",
      "Requirement already satisfied: idna<4,>=2.5 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from requests->datawrapper) (3.8)\n",
      "Requirement already satisfied: urllib3<3,>=1.21.1 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from requests->datawrapper) (2.2.2)\n",
      "Requirement already satisfied: certifi>=2017.4.17 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from requests->datawrapper) (2024.7.4)\n",
      "Requirement already satisfied: markdown-it-py>=2.2.0 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from rich->datawrapper) (4.0.0)\n",
      "Requirement already satisfied: parso<0.9.0,>=0.8.3 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from jedi>=0.16->ipython->datawrapper) (0.8.4)\n",
      "Requirement already satisfied: mdurl~=0.1 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from markdown-it-py>=2.2.0->rich->datawrapper) (0.1.2)\n",
      "Requirement already satisfied: wcwidth in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from prompt-toolkit<3.1.0,>=3.0.41->ipython->datawrapper) (0.2.13)\n",
      "Requirement already satisfied: six>=1.5 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from python-dateutil>=2.8.2->pandas->datawrapper) (1.16.0)\n",
      "Requirement already satisfied: executing>=1.2.0 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from stack-data->ipython->datawrapper) (2.0.1)\n",
      "Requirement already satisfied: asttokens>=2.1.0 in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from stack-data->ipython->datawrapper) (2.4.1)\n",
      "Requirement already satisfied: pure-eval in c:\\users\\auuser\\appdata\\roaming\\jupyterlab-desktop\\jlab_server\\lib\\site-packages (from stack-data->ipython->datawrapper) (0.2.3)\n"
     ]
    }
   ],
   "source": [
    "!pip install datawrapper"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 2,
   "id": "4c693830-8f1b-4a47-b2eb-db3db1af0fc9",
   "metadata": {
    "jupyter": {
     "source_hidden": true
    }
   },
   "outputs": [
    {
     "name": "stdout",
     "output_type": "stream",
     "text": [
      "env: DATAWRAPPER_ACCESS_TOKEN=7l8stJxHAY0iQ9ZbrQbo8E6aPMbp9oeqmVrMORiRidPw7VLzbueyPLyMJFJZ2NZ1\n"
     ]
    }
   ],
   "source": [
    "%env DATAWRAPPER_ACCESS_TOKEN=7l8stJxHAY0iQ9ZbrQbo8E6aPMbp9oeqmVrMORiRidPw7VLzbueyPLyMJFJZ2NZ1 "
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 3,
   "id": "124de713-35bc-4475-85c0-0e9b840d63bd",
   "metadata": {
    "jupyter": {
     "source_hidden": true
    }
   },
   "outputs": [],
   "source": [
    "import datawrapper as dw"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 4,
   "id": "1550f119-f352-42ef-b3f2-df7712c6e2ce",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "{'id': 1017378,\n",
       " 'email': '',\n",
       " 'name': 'makalah52005-cmyk',\n",
       " 'role': 'editor',\n",
       " 'language': 'en-US',\n",
       " 'presenceColor': 'color-dw-presence-100',\n",
       " 'avatar': 'https://avatars.githubusercontent.com/u/229180935?v=4',\n",
       " 'customAvatar': 'https://avatars.githubusercontent.com/u/229180935?v=4',\n",
       " 'teams': [],\n",
       " 'workspaces': [{'slug': 'xngzrvenjx',\n",
       "   'name': 'makalah52005-cmyk',\n",
       "   'avatar': 'https://avatars.githubusercontent.com/u/229180935?v=4',\n",
       "   'color': 'color-dw-presence-100',\n",
       "   'personalAppearance': True}],\n",
       " 'chartCount': 14,\n",
       " 'url': '/v3/users/1017378',\n",
       " 'activeTeam': None}"
      ]
     },
     "execution_count": 4,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "dw.Datawrapper().get_my_account()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 5,
   "id": "36b27d8d-541a-4aff-92fc-df77a819bd34",
   "metadata": {},
   "outputs": [],
   "source": [
    "import pandas as pd"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 6,
   "id": "524a96a7-e49b-4a47-b55c-7979aebee962",
   "metadata": {},
   "outputs": [],
   "source": [
    "df = pd.read_csv(\n",
    "    \"https://raw.githubusercontent.com/palewire/first-automated-chart/main/_notebooks/arrests.csv\",\n",
    "    parse_dates=[\"ArrestDateTime\"]\n",
    ")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 7,
   "id": "28f621e9-953d-4c29-bf7f-faf301848caf",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "<div>\n",
       "<style scoped>\n",
       "    .dataframe tbody tr th:only-of-type {\n",
       "        vertical-align: middle;\n",
       "    }\n",
       "\n",
       "    .dataframe tbody tr th {\n",
       "        vertical-align: top;\n",
       "    }\n",
       "\n",
       "    .dataframe thead th {\n",
       "        text-align: right;\n",
       "    }\n",
       "</style>\n",
       "<table border=\"1\" class=\"dataframe\">\n",
       "  <thead>\n",
       "    <tr style=\"text-align: right;\">\n",
       "      <th></th>\n",
       "      <th>RowID</th>\n",
       "      <th>X</th>\n",
       "      <th>Y</th>\n",
       "      <th>IncidentNumber</th>\n",
       "      <th>ArrestNumber</th>\n",
       "      <th>Age</th>\n",
       "      <th>Gender</th>\n",
       "      <th>Race</th>\n",
       "      <th>ArrestDateTime</th>\n",
       "      <th>ArrestLocation</th>\n",
       "      <th>...</th>\n",
       "      <th>ChargeDescription</th>\n",
       "      <th>District</th>\n",
       "      <th>Post</th>\n",
       "      <th>Neighborhood</th>\n",
       "      <th>Latitude</th>\n",
       "      <th>Longitude</th>\n",
       "      <th>GeoLocation</th>\n",
       "      <th>Shape</th>\n",
       "      <th>Year</th>\n",
       "      <th>year</th>\n",
       "    </tr>\n",
       "  </thead>\n",
       "  <tbody>\n",
       "    <tr>\n",
       "      <th>0</th>\n",
       "      <td>29</td>\n",
       "      <td>1.401347e+06</td>\n",
       "      <td>608148.870493</td>\n",
       "      <td>22L09338</td>\n",
       "      <td>23000037.0</td>\n",
       "      <td>39.0</td>\n",
       "      <td>M</td>\n",
       "      <td>B</td>\n",
       "      <td>2022-12-31 23:50:00</td>\n",
       "      <td>4000 OAKFORD ST</td>\n",
       "      <td>...</td>\n",
       "      <td>HAND GUN VIOLATION</td>\n",
       "      <td>Northwest</td>\n",
       "      <td>621.0</td>\n",
       "      <td>West Arlington</td>\n",
       "      <td>39.3361</td>\n",
       "      <td>-76.6853</td>\n",
       "      <td>(39.3361,-76.6853)</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2022</td>\n",
       "      <td>2022</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>1</th>\n",
       "      <td>30</td>\n",
       "      <td>1.401347e+06</td>\n",
       "      <td>608148.870493</td>\n",
       "      <td>22L09338</td>\n",
       "      <td>23000039.0</td>\n",
       "      <td>50.0</td>\n",
       "      <td>M</td>\n",
       "      <td>B</td>\n",
       "      <td>2022-12-31 23:50:00</td>\n",
       "      <td>4000 OAKFORD ST</td>\n",
       "      <td>...</td>\n",
       "      <td>HAND GUN VIOLATION</td>\n",
       "      <td>Northwest</td>\n",
       "      <td>621.0</td>\n",
       "      <td>West Arlington</td>\n",
       "      <td>39.3361</td>\n",
       "      <td>-76.6853</td>\n",
       "      <td>(39.3361,-76.6853)</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2022</td>\n",
       "      <td>2022</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>2</th>\n",
       "      <td>31</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>23000010.0</td>\n",
       "      <td>27.0</td>\n",
       "      <td>M</td>\n",
       "      <td>B</td>\n",
       "      <td>2022-12-31 23:40:00</td>\n",
       "      <td>NaN</td>\n",
       "      <td>...</td>\n",
       "      <td>FAILURE TO APPEAR</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>(,)</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2022</td>\n",
       "      <td>2022</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>3</th>\n",
       "      <td>32</td>\n",
       "      <td>1.417636e+06</td>\n",
       "      <td>595206.835862</td>\n",
       "      <td>22L09343</td>\n",
       "      <td>23000050.0</td>\n",
       "      <td>42.0</td>\n",
       "      <td>M</td>\n",
       "      <td>B</td>\n",
       "      <td>2022-12-31 23:15:00</td>\n",
       "      <td>500 DOLPHIN ST</td>\n",
       "      <td>...</td>\n",
       "      <td>HAND GUN VIOLATION</td>\n",
       "      <td>Central</td>\n",
       "      <td>123.0</td>\n",
       "      <td>Upton</td>\n",
       "      <td>39.3004</td>\n",
       "      <td>-76.6279</td>\n",
       "      <td>(39.3004,-76.6279)</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2022</td>\n",
       "      <td>2022</td>\n",
       "    </tr>\n",
       "    <tr>\n",
       "      <th>4</th>\n",
       "      <td>33</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>22L09312</td>\n",
       "      <td>22157183.0</td>\n",
       "      <td>43.0</td>\n",
       "      <td>F</td>\n",
       "      <td>W</td>\n",
       "      <td>2022-12-31 21:00:00</td>\n",
       "      <td>1500 BECKLOW AVE</td>\n",
       "      <td>...</td>\n",
       "      <td>STOLEN AUTO</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>NaN</td>\n",
       "      <td>(,)</td>\n",
       "      <td>NaN</td>\n",
       "      <td>2022</td>\n",
       "      <td>2022</td>\n",
       "    </tr>\n",
       "  </tbody>\n",
       "</table>\n",
       "<p>5 rows × 23 columns</p>\n",
       "</div>"
      ],
      "text/plain": [
       "   RowID             X              Y IncidentNumber  ArrestNumber   Age  \\\n",
       "0     29  1.401347e+06  608148.870493       22L09338    23000037.0  39.0   \n",
       "1     30  1.401347e+06  608148.870493       22L09338    23000039.0  50.0   \n",
       "2     31           NaN            NaN            NaN    23000010.0  27.0   \n",
       "3     32  1.417636e+06  595206.835862       22L09343    23000050.0  42.0   \n",
       "4     33           NaN            NaN       22L09312    22157183.0  43.0   \n",
       "\n",
       "  Gender Race      ArrestDateTime    ArrestLocation  ...   ChargeDescription  \\\n",
       "0      M    B 2022-12-31 23:50:00   4000 OAKFORD ST  ...  HAND GUN VIOLATION   \n",
       "1      M    B 2022-12-31 23:50:00   4000 OAKFORD ST  ...  HAND GUN VIOLATION   \n",
       "2      M    B 2022-12-31 23:40:00               NaN  ...   FAILURE TO APPEAR   \n",
       "3      M    B 2022-12-31 23:15:00    500 DOLPHIN ST  ...  HAND GUN VIOLATION   \n",
       "4      F    W 2022-12-31 21:00:00  1500 BECKLOW AVE  ...         STOLEN AUTO   \n",
       "\n",
       "    District   Post    Neighborhood Latitude  Longitude         GeoLocation  \\\n",
       "0  Northwest  621.0  West Arlington  39.3361   -76.6853  (39.3361,-76.6853)   \n",
       "1  Northwest  621.0  West Arlington  39.3361   -76.6853  (39.3361,-76.6853)   \n",
       "2        NaN    NaN             NaN      NaN        NaN                 (,)   \n",
       "3    Central  123.0           Upton  39.3004   -76.6279  (39.3004,-76.6279)   \n",
       "4        NaN    NaN             NaN      NaN        NaN                 (,)   \n",
       "\n",
       "   Shape  Year  year  \n",
       "0    NaN  2022  2022  \n",
       "1    NaN  2022  2022  \n",
       "2    NaN  2022  2022  \n",
       "3    NaN  2022  2022  \n",
       "4    NaN  2022  2022  \n",
       "\n",
       "[5 rows x 23 columns]"
      ]
     },
     "execution_count": 7,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.head()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 8,
   "id": "aaaac190-c254-49b3-a757-6a196136615d",
   "metadata": {},
   "outputs": [],
   "source": [
    "df['year'] = df.ArrestDateTime.dt.year"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 9,
   "id": "6cbc2ed2-73e9-419e-b890-7fae4e7aa76d",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "year\n",
       "2010    45224\n",
       "2011    43364\n",
       "2012    42333\n",
       "2013    39542\n",
       "2014    37078\n",
       "2015    25732\n",
       "2016    23089\n",
       "2017    21989\n",
       "2018    20543\n",
       "2019    19407\n",
       "2023    13566\n",
       "2020    13162\n",
       "2022    12360\n",
       "2021    11130\n",
       "Name: count, dtype: int64"
      ]
     },
     "execution_count": 9,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "df.year.value_counts()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 10,
   "id": "429e3445-805d-410a-8272-a5eb3b8dd934",
   "metadata": {},
   "outputs": [],
   "source": [
    "totals_by_year = df.year.value_counts().sort_index().reset_index()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 11,
   "id": "a75b8ea5-7ff4-4891-a45c-dd8cf91e7aed",
   "metadata": {},
   "outputs": [],
   "source": [
    "chart = dw.ColumnChart(\n",
    "    title=\"Baltimore Arrests\",\n",
    "    data=totals_by_year\n",
    ")"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 12,
   "id": "41e4460d-4521-4fea-ac89-026d1e84e19f",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "ColumnChart(chart_type='column-chart', data=    year  count\n",
       "0   2010  45224\n",
       "1   2011  43364\n",
       "2   2012  42333\n",
       "3   2013  39542\n",
       "4   2014  37078\n",
       "5   2015  25732\n",
       "6   2016  23089\n",
       "7   2017  21989\n",
       "8   2018  20543\n",
       "9   2019  19407\n",
       "10  2020  13162\n",
       "11  2021  11130\n",
       "12  2022  12360\n",
       "13  2023  13566, transformations=Transform(transpose=False, vertical_header=True, horizontal_header=True, column_order=[], column_format=ColumnFormatList(formats=[]), external_data='', use_datawrapper_cdn=True, upload_method='copy'), title='Baltimore Arrests', intro='', notes='', source_name='', source_url='', byline='', aria_description='', hide_title=False, language='en-US', theme='datawrapper', auto_dark_mode=False, dark_mode_invert=True, get_the_data=False, download_image=False, download_pdf=False, download_svg=False, embed=False, force_attribution=False, share_buttons=False, share_url='', logo=False, logo_id='', custom={}, forkable=True, chart_id='JN5P4', custom_ticks_x=None, custom_ticks_y=None, custom_range_x=None, custom_range_y=None, x_grid_format=None, y_grid_format=None, x_grid='off', y_grid='on', text_annotations=[], range_annotations=[], y_grid_labels='outside', y_grid_label_align='left', base_color=0, negative_color=None, color_category={}, category_labels={}, category_order=[], exclude_from_color_key=[], bar_padding=30, plot_height_mode='fixed', plot_height_fixed=300, plot_height_ratio=0.5, show_color_key=False, show_value_labels='hover', value_labels_format='', value_labels_placement='outside')"
      ]
     },
     "execution_count": 12,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.create()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 13,
   "id": "69c53cea-d4ef-4ab5-9a6b-dc1d38f4ee9f",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "ColumnChart(chart_type='column-chart', data=    year  count\n",
       "0   2010  45224\n",
       "1   2011  43364\n",
       "2   2012  42333\n",
       "3   2013  39542\n",
       "4   2014  37078\n",
       "5   2015  25732\n",
       "6   2016  23089\n",
       "7   2017  21989\n",
       "8   2018  20543\n",
       "9   2019  19407\n",
       "10  2020  13162\n",
       "11  2021  11130\n",
       "12  2022  12360\n",
       "13  2023  13566, transformations=Transform(transpose=False, vertical_header=True, horizontal_header=True, column_order=[], column_format=ColumnFormatList(formats=[]), external_data='', use_datawrapper_cdn=True, upload_method='copy'), title='Baltimore Arrests', intro='', notes='', source_name='', source_url='', byline='', aria_description='', hide_title=False, language='en-US', theme='datawrapper', auto_dark_mode=False, dark_mode_invert=True, get_the_data=False, download_image=False, download_pdf=False, download_svg=False, embed=False, force_attribution=False, share_buttons=False, share_url='', logo=False, logo_id='', custom={}, forkable=True, chart_id='JN5P4', custom_ticks_x=None, custom_ticks_y=None, custom_range_x=None, custom_range_y=None, x_grid_format=None, y_grid_format=None, x_grid='off', y_grid='on', text_annotations=[], range_annotations=[], y_grid_labels='outside', y_grid_label_align='left', base_color=0, negative_color=None, color_category={}, category_labels={}, category_order=[], exclude_from_color_key=[], bar_padding=30, plot_height_mode='fixed', plot_height_fixed=300, plot_height_ratio=0.5, show_color_key=False, show_value_labels='hover', value_labels_format='', value_labels_placement='outside')"
      ]
     },
     "execution_count": 13,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.publish()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 14,
   "id": "2b095410-fe0b-4300-8cc9-91cb05e18a95",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"400\"\n",
       "            src=\"https://datawrapper.dwcdn.net/JN5P4/1/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x19b111ba3c0>"
      ]
     },
     "execution_count": 14,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.display()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 15,
   "id": "29eca703-7376-45a5-8aa4-e4846943d7eb",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "ColumnChart(chart_type='column-chart', data=    year  count\n",
       "0   2010  45224\n",
       "1   2011  43364\n",
       "2   2012  42333\n",
       "3   2013  39542\n",
       "4   2014  37078\n",
       "5   2015  25732\n",
       "6   2016  23089\n",
       "7   2017  21989\n",
       "8   2018  20543\n",
       "9   2019  19407\n",
       "10  2020  13162\n",
       "11  2021  11130\n",
       "12  2022  12360\n",
       "13  2023  13566, transformations=Transform(transpose=False, vertical_header=True, horizontal_header=True, column_order=[], column_format=ColumnFormatList(formats=[]), external_data='', use_datawrapper_cdn=True, upload_method='copy'), title='Baltimore Arrests', intro='', notes='', source_name='OpenBaltimore', source_url='https://data.baltimorecity.gov/datasets/baltimore::bpd-arrests/about', byline='Makalah Vaughn', aria_description='', hide_title=False, language='en-US', theme='datawrapper', auto_dark_mode=False, dark_mode_invert=True, get_the_data=False, download_image=False, download_pdf=False, download_svg=False, embed=False, force_attribution=False, share_buttons=False, share_url='', logo=False, logo_id='', custom={}, forkable=True, chart_id='JN5P4', custom_ticks_x=None, custom_ticks_y=None, custom_range_x=None, custom_range_y=None, x_grid_format=None, y_grid_format=None, x_grid='off', y_grid='on', text_annotations=[], range_annotations=[], y_grid_labels='outside', y_grid_label_align='left', base_color=0, negative_color=None, color_category={}, category_labels={}, category_order=[], exclude_from_color_key=[], bar_padding=30, plot_height_mode='fixed', plot_height_fixed=300, plot_height_ratio=0.5, show_color_key=False, show_value_labels='hover', value_labels_format='', value_labels_placement='outside')"
      ]
     },
     "execution_count": 15,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.source_name = \"OpenBaltimore\"\n",
    "chart.source_url = \"https://data.baltimorecity.gov/datasets/baltimore::bpd-arrests/about\"\n",
    "chart.byline = \"Makalah Vaughn\"\n",
    "chart.update()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 16,
   "id": "0b9247aa-0a14-4238-9eaf-5581716f96fd",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "ColumnChart(chart_type='column-chart', data=    year  count\n",
       "0   2010  45224\n",
       "1   2011  43364\n",
       "2   2012  42333\n",
       "3   2013  39542\n",
       "4   2014  37078\n",
       "5   2015  25732\n",
       "6   2016  23089\n",
       "7   2017  21989\n",
       "8   2018  20543\n",
       "9   2019  19407\n",
       "10  2020  13162\n",
       "11  2021  11130\n",
       "12  2022  12360\n",
       "13  2023  13566, transformations=Transform(transpose=False, vertical_header=True, horizontal_header=True, column_order=[], column_format=ColumnFormatList(formats=[]), external_data='', use_datawrapper_cdn=True, upload_method='copy'), title='Baltimore Arrests', intro='', notes='', source_name='OpenBaltimore', source_url='https://data.baltimorecity.gov/datasets/baltimore::bpd-arrests/about', byline='Makalah Vaughn', aria_description='', hide_title=False, language='en-US', theme='datawrapper', auto_dark_mode=False, dark_mode_invert=True, get_the_data=False, download_image=False, download_pdf=False, download_svg=False, embed=False, force_attribution=False, share_buttons=False, share_url='', logo=False, logo_id='', custom={}, forkable=True, chart_id='JN5P4', custom_ticks_x=None, custom_ticks_y=None, custom_range_x=None, custom_range_y=None, x_grid_format=None, y_grid_format=None, x_grid='off', y_grid='on', text_annotations=[], range_annotations=[], y_grid_labels='outside', y_grid_label_align='left', base_color=0, negative_color=None, color_category={}, category_labels={}, category_order=[], exclude_from_color_key=[], bar_padding=30, plot_height_mode='fixed', plot_height_fixed=300, plot_height_ratio=0.5, show_color_key=False, show_value_labels='hover', value_labels_format='', value_labels_placement='outside')"
      ]
     },
     "execution_count": 16,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.publish()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 17,
   "id": "c53abbab-d0db-4baa-9dec-64b686c738cf",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"400\"\n",
       "            src=\"https://datawrapper.dwcdn.net/JN5P4/2/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x19b168a6690>"
      ]
     },
     "execution_count": 17,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.display()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 18,
   "id": "df05c131-ecbd-4353-b187-58857e078e6b",
   "metadata": {},
   "outputs": [],
   "source": [
    "chart.base_color = \"#004FA2\"  # Our accent color"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 19,
   "id": "6d7363e1-e329-4cdc-a437-201a37e4848a",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "ColumnChart(chart_type='column-chart', data=    year  count\n",
       "0   2010  45224\n",
       "1   2011  43364\n",
       "2   2012  42333\n",
       "3   2013  39542\n",
       "4   2014  37078\n",
       "5   2015  25732\n",
       "6   2016  23089\n",
       "7   2017  21989\n",
       "8   2018  20543\n",
       "9   2019  19407\n",
       "10  2020  13162\n",
       "11  2021  11130\n",
       "12  2022  12360\n",
       "13  2023  13566, transformations=Transform(transpose=False, vertical_header=True, horizontal_header=True, column_order=[], column_format=ColumnFormatList(formats=[]), external_data='', use_datawrapper_cdn=True, upload_method='copy'), title='Baltimore Arrests', intro='', notes='', source_name='OpenBaltimore', source_url='https://data.baltimorecity.gov/datasets/baltimore::bpd-arrests/about', byline='Makalah Vaughn', aria_description='', hide_title=False, language='en-US', theme='datawrapper', auto_dark_mode=False, dark_mode_invert=True, get_the_data=False, download_image=False, download_pdf=False, download_svg=False, embed=False, force_attribution=False, share_buttons=False, share_url='', logo=False, logo_id='', custom={}, forkable=True, chart_id='JN5P4', custom_ticks_x=None, custom_ticks_y=None, custom_range_x=None, custom_range_y=None, x_grid_format=None, y_grid_format=None, x_grid='off', y_grid='on', text_annotations=[], range_annotations=[], y_grid_labels='outside', y_grid_label_align='left', base_color='#004FA2', negative_color=None, color_category={}, category_labels={}, category_order=[], exclude_from_color_key=[], bar_padding=30, plot_height_mode='fixed', plot_height_fixed=300, plot_height_ratio=0.5, show_color_key=False, show_value_labels='hover', value_labels_format='', value_labels_placement='outside')"
      ]
     },
     "execution_count": 19,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.update()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 20,
   "id": "4e73627c-dd37-43fe-b154-f7663241f31a",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/plain": [
       "ColumnChart(chart_type='column-chart', data=    year  count\n",
       "0   2010  45224\n",
       "1   2011  43364\n",
       "2   2012  42333\n",
       "3   2013  39542\n",
       "4   2014  37078\n",
       "5   2015  25732\n",
       "6   2016  23089\n",
       "7   2017  21989\n",
       "8   2018  20543\n",
       "9   2019  19407\n",
       "10  2020  13162\n",
       "11  2021  11130\n",
       "12  2022  12360\n",
       "13  2023  13566, transformations=Transform(transpose=False, vertical_header=True, horizontal_header=True, column_order=[], column_format=ColumnFormatList(formats=[]), external_data='', use_datawrapper_cdn=True, upload_method='copy'), title='Baltimore Arrests', intro='', notes='', source_name='OpenBaltimore', source_url='https://data.baltimorecity.gov/datasets/baltimore::bpd-arrests/about', byline='Makalah Vaughn', aria_description='', hide_title=False, language='en-US', theme='datawrapper', auto_dark_mode=False, dark_mode_invert=True, get_the_data=False, download_image=False, download_pdf=False, download_svg=False, embed=False, force_attribution=False, share_buttons=False, share_url='', logo=False, logo_id='', custom={}, forkable=True, chart_id='JN5P4', custom_ticks_x=None, custom_ticks_y=None, custom_range_x=None, custom_range_y=None, x_grid_format=None, y_grid_format=None, x_grid='off', y_grid='on', text_annotations=[], range_annotations=[], y_grid_labels='outside', y_grid_label_align='left', base_color='#004FA2', negative_color=None, color_category={}, category_labels={}, category_order=[], exclude_from_color_key=[], bar_padding=30, plot_height_mode='fixed', plot_height_fixed=300, plot_height_ratio=0.5, show_color_key=False, show_value_labels='hover', value_labels_format='', value_labels_placement='outside')"
      ]
     },
     "execution_count": 20,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.publish()"
   ]
  },
  {
   "cell_type": "code",
   "execution_count": 21,
   "id": "96564cf1-09c0-4a59-b895-a6c018ffd64d",
   "metadata": {},
   "outputs": [
    {
     "data": {
      "text/html": [
       "\n",
       "        <iframe\n",
       "            width=\"600\"\n",
       "            height=\"400\"\n",
       "            src=\"https://datawrapper.dwcdn.net/JN5P4/3/\"\n",
       "            frameborder=\"0\"\n",
       "            allowfullscreen\n",
       "            \n",
       "        ></iframe>\n",
       "        "
      ],
      "text/plain": [
       "<IPython.lib.display.IFrame at 0x19b0ed0c3e0>"
      ]
     },
     "execution_count": 21,
     "metadata": {},
     "output_type": "execute_result"
    }
   ],
   "source": [
    "chart.display()"
   ]
  }
 ],
 "metadata": {
  "kernelspec": {
   "display_name": "Python 3 (ipykernel)",
   "language": "python",
   "name": "python3"
  },
  "language_info": {
   "codemirror_mode": {
    "name": "ipython",
    "version": 3
   },
   "file_extension": ".py",
   "mimetype": "text/x-python",
   "name": "python",
   "nbconvert_exporter": "python",
   "pygments_lexer": "ipython3",
   "version": "3.12.5"
  }
 },
 "nbformat": 4,
 "nbformat_minor": 5
}

DataWrapper Chart Link: https://datawrapper.dwcdn.net/JN5P4/3/ 
