
## Project Goal
The goal of this project is to measure the pageview traffic of a subset of Wikipedia articles related to Academy Award-winning movies from 2015 to 2023. The project aims to create three distinct datasets: monthly mobile access, monthly desktop access, and monthly cumulative pageviews.
## Data Sources
- **Wikipedia Pageviews Data**: This project relies on the Wikimedia Foundation REST API to access pageview data for Wikipedia articles. The data spans from July 2015 through the previous complete month.

## Data Processing and Analysis
The project consists of several key steps, including data acquisition, data processing, and dataset creation: 

1. **Data Acquisition**: The project uses the Pageviews API to retrieve pageview counts for specific Wikipedia articles.
   
2. **Data Processing**: The retrieved data is processed and organized into time series of monthly pageview activity.

3. **Dataset Creation**: Three datasets are created:
   - Monthly Mobile Access: Aggregated pageviews from mobile web and mobile app.
   - Monthly Desktop Access: Pageviews from desktop.
   - Monthly Cumulative: The sum of all mobile and desktop traffic per article.

## Documentation
This project adheres to best practices for reproducibility and documentation:

- Jupyter Notebook(s): Detailed documentation of data acquisition, processing, and analysis steps, with explanations in Markdown sentences.

- README File (this file): Provides an overview of the project, including goals, data sources, data processing steps, and guidelines for reproducibility.

- LICENSE File: Contains the MIT LICENSE for the code to ensure its open and fair use.

## License
This project is open-source and follows the MIT License. You are free to use and modify the code following the terms of the MIT License.

## API Documentation
- **Wikimedia Foundation REST API**: This project uses the Wikimedia Foundation REST API to access pageview data. For API documentation and terms of use, please visit: [Wikimedia Foundation REST API Documentation](https://www.mediawiki.org/wiki/REST_API#Terms_and_conditions)

## Known Issues
- Few articles returning 404 API response, meaning the URL is not found.
- For any issues with specific api related to any of the articles please refer to data owner as stated in  sourse.

## Output Files
- The project generates three JSON files:
   - `academy_monthly_mobile_201507-202312.json`: Monthly mobile access data.
   - `academy_monthly_desktop_201507-202312.json`: Monthly desktop access data.
   - `academy_monthly_cumulative_201507-202312.json`: Monthly cumulative data.

Please refer to each file for detailed data on Wikipedia pageviews.

## Analysis Steps
1. Data Collection: Data was collected from the Pageviews API using Python code.
2. Data Processing: The collected data was processed to calculate average pageviews, identify articles with the highest and lowest pageviews, and find articles with the fewest months of data.
3. Data Visualization: Three graphs were created to visualize the analysis results:
   - Maximum and Minimum Average Page Requests
   - Top 10 Peak Page Views
   - Articles with Fewest Months of Data
4. Interpretation: The analysis results were interpreted to draw insights from the data.

## Reproducing the Analysis
To reproduce this analysis, follow these steps:
1. Clone this repository to your local machine.
2. Ensure you have Python installed with the required libraries (pandas, matplotlib, json).
3. Run Jupyter Notebook data_acquisition.ipynb to generate all the required jsons
4. Run Jupyter Notebook data_analysis.ipynb to generate all graphs, which will be saved in parent folder
3. Analyze graphs


Feel free to use, modify, or contribute to this project while adhering to the MIT License.
\
---\
\
**Note**: For additional details and code implementation, please refer to the provided Jupyter Notebook(s).
