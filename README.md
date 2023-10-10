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
 4.  Modify the following parameters in the code to match your needs:
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


- src     ##Code directory (where this code is located)
	- data_acquisition.ipynb # Used to collect and store data in desired format.
	- data_analysis.ipynb # Used to view and analyse data in desired format.
- data ##Data directory (contains the CSV and JSON files)
  - thank_the_academy.AUG.2023.csv   # CSV file with article information
  - academy_monthly_mobile_201507-202312.json   # JSON file with mobile data
  - academy_monthly_desktop_201507-202312.json   # JSON file with desktop data
  - academy_monthly_cumulative_201507-202312.json   # JSON file with cumulative data
- results ##Directory for results and analysis (not included in the code)
	- fewest_months_data_pageviews.png  ## Maximum Average and Minimum Average - The first graph should contain time series for the articles that have the highest average monthly page requests and the lowest average monthly page requests for desktop access and mobile access. Your graph should have four lines (max desktop, min desktop, max mobile, min mobile).
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

## Contributing

If you have any suggestions or improvements for this README or the code itself, please feel free to contribute by submitting a pull request. Your feedback and contributions are greatly appreciated.

## License
This code is provided under the MIT License, allowing you to use and modify it freely. Please review the license for more details.

Note: This README provides an overview of the code and its usage. Make sure to adjust the code and file paths to suit your specific project requirements and folder structure.