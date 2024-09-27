# Data Modeling Project

This project involves building and populating a PostgreSQL relational database to store financial data related to countries, accounts, and series indicators. The data is sourced from CSV files, processed using Python, and inserted into a database for efficient querying and analysis.

## Project Overview

The objective of this project is to transform raw data into a well-structured relational database, ensuring proper schema design, data cleaning, and insertion using `pandas` and `psycopg2` in Python. The dataset includes information on financial accounts, country-level details, and various financial series over multiple years.

### Key Features:
- **Data Cleaning and Transformation**: Handles invalid numeric values, duplicates, and missing data before insertion.
- **Database Schema Design**: Three relational tables are designed to efficiently store and manage the data.
- **PostgreSQL Integration**: Data is inserted into a PostgreSQL database using the `psycopg2` library.
- **Error Handling**: Implements strategies for managing issues such as duplicate keys and invalid data formats during insertion.

## Files Included

- **`Data Modelling Project.ipynb`**: Jupyter notebook containing the Python code for the entire process, from data cleaning to database insertion.
- **`Wealth-AccountSeries.csv`**: CSV file containing metadata about different financial series.
- **`Wealth-AccountsCountry.csv`**: CSV file containing country-level financial information.
- **`Wealth-AccountData.csv`**: CSV file containing the actual financial data for various countries and series over different years.

## Technologies Used

- **Python**:
  - Libraries: `pandas`, `psycopg2`
- **PostgreSQL**: Used for relational database management.
- **Jupyter Notebook**: For writing and executing the code.
- **CSV**: Format of the raw data files used for analysis.

## Database Schema

The database schema includes three main tables:

1. **AccountsCountry**: Stores country-related information about financial accounts.
2. **AccountsData**: Contains financial data for different countries and financial series across multiple years.
3. **AccountsSeries**: Holds metadata about the financial indicators.

### Table Definitions:

- **AccountsCountry**:
  - `Account_Code`: Primary key
  - `Long_Name`: Full name of the account
  - `Table_Name`: Name of the table in the original data
  - `Currency_Unit`: The currency unit used in the financial data

- **AccountsData**:
  - `Country_Name`: Name of the country
  - `Country_Code`: Country code (foreign key from AccountsCountry)
  - `Series_Name`: Name of the financial series
  - `Series_Code`: Code for the financial series (foreign key from AccountsSeries)
  - `YR1995`, `YR2000`, `YR2005`, `YR2010`, `YR2014`: Financial data for respective years

- **AccountsSeries**:
  - `Code`: Series code (primary key)
  - `Topic`: General topic of the series
  - `Indicator_Name`: Specific indicator name of the series
  - `Long_Definition`: Full definition of the financial indicator

## How to Run the Project

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/data-modeling-project.git
   cd data-modeling-project
   ```

2. **Install the Required Libraries**:
   Install the Python libraries using the `requirements.txt` (ensure you have PostgreSQL installed on your machine).
   ```bash
   pip install -r requirements.txt
   ```

3. **Set Up PostgreSQL**:
   - Ensure you have a running instance of PostgreSQL.
   - Modify the connection settings in the Jupyter notebook (`Data Modelling Project.ipynb`) as per your PostgreSQL setup.

4. **Run the Jupyter Notebook**:
   Execute the notebook `Data Modelling Project.ipynb`. It will:
   - Clean and process the CSV data.
   - Create the required database schema.
   - Insert the cleaned data into the PostgreSQL database.

5. **Explore the Data**:
   Once the data is inserted into the database, you can run SQL queries to explore and analyze the financial data.

## Data Source

The data used in this project was sourced from publicly available datasets and transformed for the purpose of this modeling exercise. The main CSV files included in the project are:
- **Wealth-AccountSeries.csv**
- **Wealth-AccountsCountry.csv**
- **Wealth-AccountData.csv**
