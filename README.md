# CircleCI Usage Report Visualization Dashboard

> ⚠️ **WARNING:** This Usage Report Visualization Dashboard is provided on an 'as-is' and 'as available' basis without any warranties of any kind. CircleCI disclaims all warranties, express or implied, including, but not limited to, all implied warranties of merchantability, title, fitness for a particular purpose, and noninfringement.

A lightweight, browser-based dashboard for analyzing CircleCI usage metrics to optimize CI/CD costs and performance through detailed resource utilization insights.

## Features

This dashboard provides comprehensive visualizations to help you understand your CircleCI usage patterns and optimize resource allocation:

### Usage Analytics
1. **Daily/Weekly Credit Burn Rate**
   * Track your credit usage over time
   * Toggle between daily and weekly views
   * Identify trends and anomalies in usage patterns

2. **Top 10 Credit Consuming Projects**
   * Identify which projects are using the most credits
   * Focus optimization efforts where they'll have the biggest impact

3. **Top 10 Credit Consuming Workflows**
   * See which specific workflows are most expensive
   * Includes project name for context

4. **Top 10 Credit Consuming Jobs**
   * Pinpoint the exact jobs that consume the most credits
   * Target specific jobs for optimization

5. **Credit Usage by Resource Class**
   * Understand which resource classes consume the most credits
   * Identify opportunities to right-size resource classes

### Resource Utilization Insights
6. **CPU & RAM Utilization Analytics**
   * View detailed CPU and RAM utilization distribution across all jobs
   * Identify underutilized and underprovisioned resources
   * Get recommendations for right-sizing resource classes

7. **Underutilized Jobs Analysis**
   * See jobs with both CPU and RAM utilization ≤ 40%
   * Calculate potential credit savings from right-sizing
   * Get specific resource class recommendations

8. **Underprovisioned Jobs Detection**
   * Identify jobs with CPU or RAM utilization ≥ 80%
   * Determine which jobs might need larger resource classes
   * Prevent performance bottlenecks before they affect builds
  
#### Important Note on Resource Utilization Analysis - Data Handling for Missing or `\\N` Values: 
- Jobs with missing (`\\N`) values in CPU or RAM utilization metrics are included in the **total job count** and all general analyses
- These jobs are only excluded from being categorized as "underutilized" or "underprovisioned" in the resource utilization section
- If your usage report contains many jobs with missing utilization data, the underutilization and underprovisioning counts may appear lower than expected

The resource utilization analysis provides insights based only on jobs with valid utilization metrics. For the most accurate results, ensure your CircleCI usage report includes complete CPU and RAM utilization data.

### Performance Optimization
9. **Top 10 Longest Running Jobs**
   * Find jobs with the longest average duration
   * Target these for optimization to reduce both time and cost

10. **Top 10 Failed Jobs by Credit Cost**
    * Discover which failed jobs are wasting the most credits
    * Prioritize fixing these jobs to reduce wasted resources

11. **Comprehensive Success Rate Analytics**
    * Monitor overall job success rates
    * Track average job duration across your CircleCI usage

## How to Use

### Access the Dashboard
You can use the dashboard directly from GitHub Pages: https://hennaabbas.github.io/circleci-usage-report-visualizer/
You may also run the code locally (see Local Development section below) 

### Getting Your CircleCI Usage Report
You can obtain your CircleCI usage data in two ways:

#### Option 1: Using the generate_cci_usage_report Script
You can use the generate_cci_usage_report script to help automate the process of creating and retrieving usage reports: https://github.com/CircleCI-Public/generate_cci_usage_report

#### Option 2: Manual Download from CircleCI
1. You can manually create and retrieve your usage report by using the CircleCI v2 API `/usage` endpoints: https://circleci.com/docs/api/v2/index.html#tag/Usage
2. You can find full instructions listed in this support article: https://support.circleci.com/hc/en-us/articles/28730291589403-How-to-use-the-CircleCI-v2-API-to-create-and-retrieve-usage-reports

### Required CSV Format
For full functionality, your usage report should include the following columns:
- Standard usage columns: `PROJECT_NAME`, `JOB_NAME`, `WORKFLOW_NAME`, `RESOURCE_CLASS`, `JOB_BUILD_STATUS`, `JOB_RUN_SECONDS`, `TOTAL_CREDITS`, `JOB_RUN_DATE`, `PIPELINE_CREATED_AT`, `VCS_BRANCH`
- Resource utilization columns: `MEDIAN_CPU_UTILIZATION_PCT`, `MEDIAN_RAM_UTILIZATION_PCT`

Note: Resource utilization analysis will only be available if your CSV includes the utilization percentage columns.

### Analyzing Your Data
1. Upload your CircleCI usage report CSV file using the file input
2. The dashboard will automatically analyze the data and display all visualizations
3. Toggle between daily and weekly credit burn rates using the buttons
4. Switch between underutilized and underprovisioned jobs using the tabs
5. Download detailed reports for further analysis using the buttons at the bottom:
   - Complete usage report
   - Underutilized jobs report
   - Underprovisioned jobs report
     
**Note**: The data in this dashboard only represents credit consumption from CircleCI jobs. It does not include credits used for user seats or other organizational charges. For a complete picture of your CircleCI costs, please refer to your Plans page in the CircleCI UI.  
  

## Making Changes Based on Insights

### Right-sizing Resource Classes
Based on the dashboard's recommendations:
1. Identify jobs running on oversized resource classes (low CPU/RAM utilization)
2. Modify your `.circleci/config.yml` file to use the suggested resource classes
3. Monitor performance after changes to ensure jobs still run effectively

### Optimizing Failed Jobs
1. Focus on the top failed jobs by credit cost
2. Investigate failure patterns and implement fixes
3. Consider implementing retry policies only for critical jobs

### Addressing Long-Running Jobs
1. Target the longest-running jobs for optimization
2. Consider strategies like parallelization, caching, or reduced test scope
3. Implement test splitting for long test suites

> ## Privacy and Security
> This dashboard:
> * Runs entirely in your browser
> * Never sends your data to any server
> * Processes all data locally using JavaScript
> * Doesn't store your CircleCI data anywhere

## Local Development
To run or modify this dashboard locally:
1. Clone the repository:

```
git clone https://github.com/your-username/circleci-credit-report-visualizer.git
cd circleci-credit-report-visualizer
```

2. Open `index.html` in your browser or use a local development server:

   - **Simple option**: Just open the `index.html` file directly in your browser
     or
   - **Using a local server**: For the best experience, run it on a local development server:

```
# Python 3
python -m http.server

# Or with Node.js
npx serve
```



## Technologies Used
* HTML/CSS/JavaScript
* Tailwind CSS for styling
* Chart.js for visualizations
* PapaParse for CSV parsing
* Lodash for data manipulation

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.
1. Fork the repository from HennaAbbas/circleci-credit-report-visualizer
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request to the main repository

## Support
If you encounter any issues, have questions, want to add a feature request or share feedback, please open an issue on GitHub.
