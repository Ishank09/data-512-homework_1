
[![GitHub license](https://img.shields.io/github/license/ishank09/data-512-homework_1)](https://github.com/ishank09/data-512-homework_1/blob/main/LICENSE)

  

# Wikipedia Pageviews Data Collection

This README provides an overview of the Python code for collecting Wikipedia pageviews data for a list of articles using the Wikimedia REST API. The code reads article information from a CSV file, calls the API for each article to retrieve pageviews data, and stores the results in JSON files. Additionally, it sorts the articles by name and handles error cases gracefully. The code presented also demonstrates the process of loading JSON data, converting it into pandas DataFrames, calculating averages, identifying articles with the highest and lowest pageviews, and creating various plots to visualize the data.

# Table of Contents

[Prerequisites](##Prerequisites)

[Getting Started](##GettingStarted)

[Usage](##Usage)

[Folder Structure](##FolderStructure)

[Analysis Steps](##AnalysisSteps)

[Data Visualization](##DataVisualization)

[Reproducing the Analysis](##ReproducingtheAnalysis)

[Resources](##Resources)

[Contributing](##Contributing)

[License](##License)

  

## Prerequisites

Before using this code, ensure you have the following prerequisites installed:

  

- Python 3.x

- Required Python packages (you can install them using pip):

  - pandas
  
  - tqdm
  
  - requests

  

## Getting Started

  

1. Clone the repository or download the code to your local machine.

2. Navigate to the directory where the code is located.

3. Make sure you have a CSV file containing the article information. The CSV file should include at least two columns: "name" and "url". The "name" column contains the article names, and the "url" column

contains the URLs for the articles.

4. Modify the following parameters in the code to match your needs:

- base_api_url: The base URL of the Wikimedia API. mobile_web_suffix,

- mobile_app_suffix, desktop_suffix: API endpoints for mobile web,

- mobile app, and desktop data. granularity: The date range for which

- you want to collect data. headers: User-Agent header for API

- requests.

5. Run the code by executing it in your Python environment.

  

## Usage

The code performs the following steps:

1. Reads the article information from the CSV file and sorts them by name.

2. Iterates through each article in the CSV file and calls the Wikimedia API to retrieve pageviews data for mobile web, mobile app, and desktop.

3. Parses the API responses and stores the data in dictionaries.

4. Calculates cumulative data by combining mobile and desktop pageviews.

5. Saves the collected data in JSON files.

6. Handles error cases gracefully and prints error messages if data retrieval fails for any article.

  

After running the code, you will have three JSON files (academy_monthly_mobile_201507-202312.json, academy_monthly_desktop_201507-202312.json, and academy_monthly_cumulative_201507-202312.json) containing the pageviews data for each article.

  

## Folder Structure

The code assumes the following folder structure:

  
  

- src ##Code directory (where this code is located)

  - data_acquisition.ipynb # Used to collect and store data in desired format.
  
  - data_analysis.ipynb # Used to view and analyse data in desired format.

- data ##Data directory (contains the CSV and JSON files)

  - thank_the_academy.AUG.2023.csv # CSV file with article information
  
  - academy_monthly_mobile_201507-202312.json # JSON file with mobile data
  
  - academy_monthly_desktop_201507-202312.json # JSON file with desktop data
  
  - academy_monthly_cumulative_201507-202312.json # JSON file with cumulative data

- results ##Directory for results and analysis (not included in the code)

  - fewest_months_data_pageviews.png ## Maximum Average and Minimum Average - The first graph should contain time series for the articles that have the highest average monthly page requests and the lowest average monthly page requests for desktop access and mobile access. Your graph should have four lines (max desktop, min desktop, max mobile, min mobile).
  
  - max_min_average_page_requests.png: ## Top 10 Peak Page Views - The second graph should contain time series for the top 10 article pages by largest (peak) page views over the entire time by access type. You first find the month for each article that contains the highest (peak) page views, and then order the articles by these peak values. Your graph should contain the top 10 for desktop and top 10 for mobile access (20 lines).
  
  - top_10_peak_pageviews.png: ## Fewest Months of Data - The third graph should show pages that have the fewest months of available data. These will all be relatively short time series and should contain a set of the most recent academy award winners. Your graph should show the 10 articles with the fewest months of data for desktop access and the 10 articles with the fewest months of data for mobile access.

  

## Analysis Steps

  

1. Data Collection: Data was collected from the Pageviews API using Python code.

  

2. Data Processing: The collected data was processed to calculate average pageviews, identify articles with the highest and lowest pageviews, and find articles with the fewest months of data.

  

3. Data Visualization: Three graphs were created to visualize the analysis results:

  
  
  - Maximum and Minimum Average Page Requests
  
    
  
  - Top 10 Peak Page Views
  
    
  
  - Articles with Fewest Months of Data

  

4. Interpretation: The analysis results were interpreted to draw insights from the data.

  

## Data Visualization

  

The data_analysis.ipynb code includes code snippets for creating various plots to visualize the data. These plots include:

  

### Maximum Average and Minimum Average Pageviews

  

A line plot showing the maximum and minimum average pageviews for both mobile and desktop access types over time.

  

### Top 10 Peak Page Views Over Time

  

A line plot displaying the pageviews over time for the top 10 articles with peak pageviews, including both mobile and desktop access.

  

### Articles with Fewest Months of Data

  

A line plot illustrating the pageviews over time for articles with the fewest months of data, considering both mobile and desktop access.

  

Each plot is saved as a PNG file for reference and analysis.

  

## Reproducing the Analysis

  

To reproduce this analysis, follow these steps:

  

1. Clone this repository to your local machine.

  

2. Ensure you have Python installed with the required libraries (pandas, matplotlib, json). Install all libraries from requirements.txt.

  

3. If you want to add/edit the article list, for which you want to analysis data, please edit the file thank_the_academy.AUG.2023.csv in data folder.

  

4. If you want to change the user agents or other api details, please go through code and make changes accordingly.

  

5. Run Jupyter Notebook data_acquisition.ipynb in src folder to generate all the required jsons. After running data_acquisition.ipynb, you will generate 3 jsons files in data folder. Please go through folder structure to get better quality.

  

6. Run Jupyter Notebook data_analysis.ipynb to generate all graphs. After running data_analysis.ipynb, you will generate 3 jpeg files in results folder. Please go through folder structure to get better quality.

  

7. Analyze graphs

  

## Data

  

### Data Description

  

The data used for this analysis consists of monthly pageview statistics for a set of articles. It is stored in JSON files in the `data` directory. There are two JSON files: `academy_monthly_mobile_201507-202312.json` and `academy_monthly_desktop_201507-202312.json`. These files contain pageview data for mobile and desktop access, respectively.

json explanation:

- The JSON object contains multiple key-value pairs, where each key represents the title of an article, and the corresponding value is another JSON object.

- Within each article's JSON object, there are additional key-value pairs. Each key corresponds to a specific month in the format "YYYYMM," and the corresponding value represents the number of pageviews for that article in that specific month.

Here's a more detailed explanation of the data schema:

```json
{
  "Everything Everywhere All at Once": {
    "202001": 3515,
    "202002": 8051,
    "202003": 7159,
    "202004": 14354,
    "202005": 12061,
    ...
    "202308": 276982,
    "202309": 223715
  },
  "All Quiet on the Western Front (2022 film)": {
    "202110": 1804,
    "202111": 2917,
    "202112": 4047,
    "202201": 5195,
    "202202": 6287,
    ...
  },
  // Other articles may follow...
}
```

In summary:

- The top-level keys represent article titles, and each key corresponds to a specific article.

- Within each article's JSON object, the nested key-value pairs represent the monthly pageview data for that article. The keys follow the format "YYYYMM" to indicate the year and month of the data, while the values represent the number of pageviews for that particular month.

This data structure allows you to easily access and analyze pageview statistics for different articles over time.
  


Page View API request:
 This API is used to retrieve pageview statistics for articles on Wikipedia. Let's break down the structure of the JSON response:

```json
{
  "items": [
    {
      "project": "en.wikipedia",
      "article": "Everything_Everywhere_All_at_Once",
      "granularity": "monthly",
      "timestamp": "2023090100",
      "access": "all-access",
      "agent": "user",
      "views": 223715
    },
    {
      "project": "en.wikipedia",
      "article": "Everything_Everywhere_All_at_Once",
      "granularity": "monthly",
      "timestamp": "2023080100",
      "access": "all-access",
      "agent": "user",
      "views": 276982
    },
    // More items for other months...
  ]
}
```

Here's an explanation of the key components of this JSON response:

- `"items"`: This is the key that holds an array of items, where each item represents pageview statistics for a specific article and month.

- Each item in the array corresponds to a specific set of pageview statistics for an article in a given month.

  - `"project"`: This key specifies the Wikimedia project, which is "en.wikipedia" for the English Wikipedia.

  - `"article"`: This key provides the title of the article for which pageview statistics are reported.

  - `"granularity"`: Specifies the time granularity of the data, which is typically "monthly" in this context.

  - `"timestamp"`: Represents the timestamp in the format "YYYYMMDDHH," indicating the year, month, day, and hour when the pageview statistics were collected.

  - `"access"`: Indicates the type of access, which can be "all-access," "mobile-app," or "desktop."

  - `"agent"`: Specifies the user agent, which can be "user" for human users or other values for different types of access.

  - `"views"`: Represents the number of pageviews for the article in the specified month, under the given access and agent conditions.

In summary, the Pageview API response provides a structured representation of pageview statistics for articles on Wikipedia. It includes information about the article, the time period of the statistics, the type of access, and the actual number of pageviews for that combination of factors. This data is useful for tracking the popularity and viewership of articles over time.

Please refer resources for documentation and data source.

### Attributions

  

The pageview data is sourced from Wikimedia via their REST API. Attribution for the data should be given to Wikimedia.

  

### Provenance

  

The data was collected using the Wikimedia REST API with specific parameters to retrieve pageview statistics for the chosen articles. The data ranges from July 2015 to Sept 2023.

  

## Code

  

The code for this analysis is provided in Python and is available in the `src` directory. It includes scripts for data loading, data manipulation, calculations, and visualization.

  

## Analysis
The analysis includes the following steps:
### Average Pageviews
The code calculates the average pageviews for each article over the entire time period for both mobile and desktop access.

  

### Highest and Lowest Pageviews

  

It identifies the articles with the highest and lowest average pageviews for both mobile and desktop access.

  

### Top 10 Peak Pageviews

  

A DataFrame is created to list the top 10 peak pageviews for each access type (mobile and desktop).

  

### Articles with Fewest Months of Data

  

Another DataFrame is generated to display articles with the fewest months of data available.

  

## Plots

  

### Maximum and Minimum Average Pageviews

  

A plot is created to visualize the maximum and minimum average page requests over time for both mobile and desktop access.

  ![Maximum and Minimum Average Pageviews](/results/max_min_average_page_requests.png)


### Top 10 Peak Page Views

  

A plot displays the top 10 peak pageviews over time for both mobile and desktop access.
  ![Top 10 Peak Page Views](/results/top_10_peak_pageviews.png)

  

### Articles with Fewest Months of Data

  

A plot shows articles with the fewest months of data available.
  ![Articles with Fewest Months of Data](/results/fewest_months_data_pageviews.png)

  

## Resources

  

- [Wikimedia REST API Documentation](https://wikimedia.org/api/rest_v1/metrics/pageviews/per-article/en.wikipedia)

- [Practice of Reproducible Research](https://www.practicereproducibleresearch.org/)

  

Please refer to the above resources for more information about the Wikimedia API and principles of reproducible research.

In the "Resources

## Contributing

  

If you have any suggestions or improvements for this README or the code itself, please feel free to contribute by submitting a pull request. Your feedback and contributions are greatly appreciated.

  

## License

This code is provided under the MIT License, allowing you to use and modify it freely. Please review the license for more details.

  

Note: This README provides an overview of the code and its usage. Make sure to adjust the code and file paths to suit your specific project requirements and folder structure.

  
  
  
  
  
