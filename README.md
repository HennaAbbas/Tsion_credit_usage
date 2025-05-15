# CircleCI Usage Report Visualization Dashboard
> ⚠️ **WARNING:** This Usage Report Visualization Dashboard is provided 'as-is' and 'as available' basis without any warranties of any kind. CircleCI disclaims all warranties, express or implied, including, but not limited to, all implied warranties of merchantability, title, fitness for a particular purpose, and noninfringement.

A lightweight, browser-based dashboard for analyzing CircleCI usage metrics to optimize CI/CD costs and performance.

## Features

This dashboard provides six key visualizations to help you understand your CircleCI usage patterns:

1. **Top 10 Credit Consuming Projects**
   - Identify which projects are using the most credits
   - Focus optimization efforts where they'll have the biggest impact

2. **Top 10 Credit Consuming Workflows**
   - See which specific workflows are most expensive
   - Includes project name for context

3. **Top 10 Longest Running Jobs**
   - Find jobs with the longest average duration
   - Target these for optimization to reduce both time and cost

4. **Credit Usage by Resource Class**
   - Understand which resource classes consume the most credits
   - Identify opportunities to downsize resource classes where appropriate

5. **Daily/Weekly Credit Burn Rate**
   - Track your credit usage over time
   - Toggle between daily and weekly views
   - Identify trends and anomalies in usage patterns

6. **Top 10 Failed Jobs by Credit Cost**
   - Discover which failed jobs are wasting the most credits
   - Prioritize fixing these jobs to reduce wasted resources

## How to Use

### Access the Dashboard

You can use the dashboard directly from GitHub Pages:
https://hennaabbas.github.io/Tsion_credit_usage/

### Getting Your CircleCI Usage Report

You can obtain your CircleCI usage data in two ways:

#### Option 1: Using the generate_cci_usage_report Script

CircleCI provides the [generate_cci_usage_report](https://github.com/CircleCI-Public/generate_cci_usage_report) script to help automate the process of creating and retrieving usage reports.

#### Option 2: Manual Download from CircleCI

1. You can manually create and retrieve your usage report by using the CircleCI v2 API `/usage` endpoints : https://circleci.com/docs/api/v2/index.html#tag/Usage
2. You can find full instructions listed in this support article: https://support.circleci.com/hc/en-us/articles/28730291589403-How-to-use-the-CircleCI-v2-API-to-create-and-retrieve-usage-reports

### Analyzing Your Data

1. Upload your CircleCI usage report CSV file using the file input
2. The dashboard will automatically analyze the data and display all visualizations:
   - Top 10 credit consuming projects
   - Top 10 credit consuming workflows
   - Top 10 longest running jobs
   - Credit usage by resource class
   - Daily/weekly credit burn rate
   - Top 10 failed jobs by credit cost
3. Use the toggle buttons to switch between daily and weekly credit burn rates
4. Download a detailed report for further analysis using the button at the bottom

## Privacy and Security

This dashboard:
- Runs entirely in your browser
- Never sends your data to any server
- Processes all data locally using JavaScript
- Doesn't store your CircleCI data anywhere

## Local Development

To run or modify this dashboard locally:

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/circleci-insights-dashboard.git
   cd circleci-insights-dashboard
   ```

2. Open `index.html` in your browser or use a local development server:
   ```bash
   # Python 3
   python -m http.server
   
   # Or with Node.js
   npx serve
   ```

3. Make any desired changes to `index.html`

## Technologies Used

- HTML/CSS/JavaScript
- [Tailwind CSS](https://tailwindcss.com/) for styling
- [Chart.js](https://www.chartjs.org/) for visualizations
- [PapaParse](https://www.papaparse.com/) for CSV parsing
- [Lodash](https://lodash.com/) for data manipulation


## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the repository from [HennaAbbas/Tsion_credit_usage](https://github.com/HennaAbbas/Tsion_credit_usage)
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request to the main repository

## Support

If you encounter any issues or have questions, please [open an issue](https://github.com/HennaAbbas/Tsion_credit_usage/issues/new) on GitHub.
