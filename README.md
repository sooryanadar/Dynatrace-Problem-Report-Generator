# Dynatrace Data Fetcher

This Python application allows you to fetch problem data from the Dynatrace API, process the data, and save it into an Excel file. The tool offers a graphical user interface (GUI) built with Tkinter to simplify the interaction.

## Features

- Fetch data from Dynatrace API
- Filter problems by date and time range
- Export data into an Excel file with raw data and a pivot table
- Supports pagination to retrieve large datasets
- Configurable management zones and API token

## Prerequisites

Make sure you have the following Python packages installed:

- `requests`
- `pandas`
- `openpyxl`
- `tkcalendar`
- `tkinter` (usually bundled with Python)

You can install the required packages using pip:

```bash
pip install requests pandas openpyxl tkcalendar
Usage
1. Clone the Repository
To get started, clone the repository to your local machine:

bash
Copy code
git clone https://github.com/your-username/dynatrace-data-fetcher.git
cd dynatrace-data-fetcher
2. Install Dependencies
Make sure you have Python 3.x installed on your system. Then, install the required dependencies using pip:

bash
Copy code
pip install -r requirements.txt
Alternatively, if you don't have a requirements.txt file, you can install each package manually:

bash
Copy code
pip install requests pandas openpyxl tkcalendar
3. Run the Application
Run the script using Python:

bash
Copy code
python problem_report.py
4. Input Data
In the GUI, you will need to input the following details:

Dynatrace API URL: Enter your Dynatrace environment API URL:

SaaS:
bash
Copy code
https://<your-environment-id>.live.dynatrace.com/api/v2/problems
Managed:
bash
Copy code
https://<your-domain-name>/e/{your-environment-id}/api/v2/problems
From Date and Time: Select the starting date and time to filter the problems.

To Date and Time: Select the ending date and time for the data.

Management Zone: Input the management zone (e.g., Production, Staging).

API Token: Enter your Dynatrace API token.

5. Fetch Data
Once you have filled in the necessary fields, click the Fetch Data button. The application will retrieve the problem data from Dynatrace based on your input.

6. Save the Output
After the data is fetched, you will be prompted to choose a location to save the Excel file. The file will contain the following sheets:

Raw Data: Contains the problem data.
Repetitive Index: A pivot table grouping problems by Impact Level and Severity Level.
7. Check Results
Once the file is saved, you can open it in Excel to view the data.
