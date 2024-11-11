# Crash Analysis Application
Overview
This project is a data analytics application designed to perform various analyses on a crash dataset. The application is modular, following software engineering best practices, and it is built using PySpark’s DataFrame APIs to handle large datasets efficiently.

The dataset consists of six CSV files, with a corresponding data dictionary provided to explain each field. The application is designed to be config-driven and command-line executable, making it easy to adjust input and output data paths, as well as other configurations.

Project Structure
```
project-root/
│
├── src/
│   ├── __init__.py
│   ├── data_loader.py         # Loads and prepares the dataset
│   ├── analytics.py           # Contains individual analysis functions
│   ├── utils.py               # Helper functions for the application
│   ├── config_loader.py       # Loads configuration files
│
├── config/
│   └── config.yaml            # Config file for data paths and other settings
│
├── main.py                    # Entry point for executing the application
├── README.md                  # Project documentation
└── requirements.txt           # Required Python packages
```

## Dataset

The dataset consists of six CSV files located in the Data Set folder. The data dictionary provides information on the columns available in the dataset and is necessary for understanding and performing the required analyses.

## Analytics Performed

The application performs the following analyses and stores each result:

**Analysis 1:** Counts crashes with more than two male fatalities.  

**Analysis 2:** Counts crashes involving two-wheelers.  

**Analysis 3:** Lists the top 5 vehicle makes in crashes where the driver died, and airbags didn’t deploy.  

**Analysis 4:** Counts vehicles with licensed drivers involved in hit-and-run crashes.  

**Analysis 5:** Identifies the state with the highest accidents excluding female involvement.  

**Analysis 6:** Finds the 3rd to 5th vehicle makes with the most injuries or fatalities.  

**Analysis 7:** For each body style, lists the top ethnic group involved in crashes.  

**Analysis 8:** Lists the top 5 zip codes for crashes where alcohol contributed to the crash.  

**Analysis 9:** Counts distinct crashes with no property damage, damage level >4, and insured cars.  

**Analysis 10:** Lists the top 5 vehicle makes in crashes involving speeding-related charges, licensed drivers, specific colors, and top offending states.


## Setup Instructions
1. Clone or Download the Project:
   ```
   git clone <repository-url>
   cd project-root
   ```
2. **Configuration**: Update config/config.yaml with paths to the input CSV files and specify the output path for storing results.
```
input_data:
  data_folder: "path/to/dataset/folder"
output_data:
  results_folder: "path/to/output/folder"
```

## Running the Application

The application is executed using spark-submit:

```
spark-submit main.py --config config/config.yaml
```

This command initiates all analyses and stores each result in the specified output directory.

## Code Structure and Best Practices
The project follows a modular design and includes:

**Classes and Functions**: Code is organized into classes and functions to keep the structure clean and maintainable.

**DataFrame APIs**: Only DataFrame APIs are used for efficient processing and to avoid dependency on Spark SQL.

**Docstrings**: Each function includes docstrings explaining its purpose and usage.

**Config-Driven Design**: All input/output paths and other settings are specified in config.yaml for flexibility.


## Output
Results of each analysis are saved as files in the specified output folder, defined in the config.yaml.


