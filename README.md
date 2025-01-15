Dynatrace Data Fetcher - README
Overview
The Dynatrace Data Fetcher is a Flask web application designed to fetch data from the Dynatrace API based on a given date range and management zone. The application processes the fetched data and generates an Excel report with relevant problem information and pivot tables. This application helps users retrieve and analyze problem data, such as severity and impact levels, from their Dynatrace environment.

Features
Fetches problem data from Dynatrace using API tokens and user-defined filters (date range, management zone).
Converts the start and end times to human-readable formats.
Saves the fetched data into an Excel file (.xlsx).
Creates two sheets in the Excel file:
Raw Data: Contains a raw table with problem details.
Repetitive Index: A pivot table that summarizes the count of problems by impact level and severity level.
Formats the Excel sheets, such as adding bold headers, yellow highlighting, and auto filters.
Requirements
Before running the application, ensure you have the following Python packages installed:

Flask
pandas
requests
openpyxl
You can install these dependencies using pip:

bash
Copy code
pip install Flask pandas requests openpyxl
How to Run
1. Clone or Download the Project
Clone or download the project files to your local machine.

2. Application Configuration
Open the app.py file and configure any application-specific settings as needed (such as API endpoint URL or other parameters).
Ensure you have a valid Dynatrace API token with sufficient access rights to fetch the required data.
3. Run the Flask Application
Start the Flask application by running:

bash
Copy code
python app.py
This will run the server on http://127.0.0.1:5000/. You can access the web interface using a browser.

4. Interact with the Web Interface
Open a browser and navigate to http://127.0.0.1:5000/ (or http://<your-server-ip>:5000/ if running on a server).
You will see a form where you need to input the following parameters:
URL: The Dynatrace API URL.
From: The start date in the format YYYY-MM-DD.
To: The end date in the format YYYY-MM-DD.
Management Zone: The management zone to filter the data.
Token: Your Dynatrace API token.
After filling in the required information, click the "Fetch Data" button to retrieve the data.
5. Download the Generated Excel File
After the data is fetched successfully, the application will generate an Excel file (dynatrace_problems.xlsx) with the following content:

Raw Data Sheet:

Columns: Problem ID, Display ID, Title, Impact Level, Severity Level, Status, Root Cause Entity, Start Time, End Time, Management Zones.
The headers are bolded, and the first row is highlighted in yellow.
Auto-filter is applied to all columns.
Repetitive Index Sheet:

A pivot table that shows the count of problems grouped by Impact Level and Severity Level.
The Excel file will be available for download.

API Token
You need a valid Dynatrace API token to interact with the API. To generate one, follow the steps below:

Log in to your Dynatrace account.
Go to Access Tokens -> Generate new token -> Token name -> Search Scope -> Read Problems.
Generate a new API token with the necessary permissions to fetch problem data.