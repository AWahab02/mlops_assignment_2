# mlops_assignment_2

# Airflow DAG: Extract, Transform, Load Data

## Overview
This Airflow DAG (`extract_transform_load_data_dag`) is designed to automate the extraction, transformation, and loading of data from the BBC and Dawn websites. It utilizes PythonOperator to execute Python functions for each step of the process.

## Steps

1. **Extract Data**: This step extracts data by scraping articles from both the BBC and Dawn websites, saving the data to a CSV file.

2. **Transform Data**: The extracted data is transformed by converting the titles to uppercase, and then saved to a new CSV file.

3. **Load Data**: The transformed data is loaded into the project directory and pushed to Google Drive using Data Version Control (DVC). Git is used to manage version control, and changes are pushed to the GitHub repository.

## Code Structure

- **`extract_data()`**: This function extracts articles data from both websites, saves it to a CSV file, and prints the total number of links processed.
  
- **`transform_data()`**: This function reads the extracted data from the CSV file, transforms it by converting titles to uppercase, and saves the transformed data to a new CSV file.
  
- **`load_data()`**: This function initializes DVC, adds the transformed data file to DVC, adds Google Drive remote as default, pushes data to Google Drive, adds all files to the Git index, commits changes, and pushes changes to GitHub.
  
- **`default_args`**: Defines default arguments for the DAG.

- **DAG Configuration**: Configures the DAG with the necessary parameters.

## Usage
To use this DAG:
1. Install Airflow and necessary dependencies.
2. Copy the provided code into your Airflow environment.
3. Ensure that the necessary libraries (`requests`, `beautifulsoup4`, `csv`) are installed.
4. Update the file paths and URLs as needed.
5. Trigger the DAG manually or set up a schedule as per your requirements.

## Note
- Ensure proper permissions and credentials are configured for accessing the websites and Google Drive.
- Customize the code according to your project requirements and environment setup.
