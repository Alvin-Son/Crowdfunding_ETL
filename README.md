# Crowdfunding_ETL

## Project Overview
For this project, I built an end-to-end ETL pipeline using Python, Pandas, and PostgreSQL to process and organize crowdfunding data. I started by extracting data from multiple Excel files, then cleaned and transformed it into separate DataFrames for categories, subcategories, campaigns, and contacts. I used regular expressions and string methods to clean up messy contact info, split full names, and standardize email formats. Once the data was cleaned, I exported it as CSV files and designed a relational database schema with proper primary and foreign keys. Finally, I created the PostgreSQL database, built out the tables, and loaded in all the data to make it ready for analysis.


## Instructions

### 1. Create the Category and Subcategory DataFrames

#### Category DataFrame

1. Extract and transform the `crowdfunding.xlsx` Excel data to create a category DataFrame.
2. The DataFrame should have the following columns:
   - `category_id`: Sequential entries from "cat1" to "catn".
   - `category`: Category titles.
3. Export the category DataFrame as `category.csv` and save it to the repository.

#### Subcategory DataFrame

1. Extract and transform the `crowdfunding.xlsx` Excel data to create a subcategory DataFrame.
2. The DataFrame should have the following columns:
   - `subcategory_id`: Sequential entries from "subcat1" to "subcatn".
   - `subcategory`: Subcategory titles.
3. Export the subcategory DataFrame as `subcategory.csv` and save it to the repository.

### 2. Create the Campaign DataFrame

1. Extract and transform the `crowdfunding.xlsx` Excel data to create a campaign DataFrame.
2. The DataFrame should have the following columns:
   - `cf_id`
   - `contact_id`
   - `company_name`
   - `description` (formerly `blurb`)
   - `goal` (float)
   - `pledged` (float)
   - `outcome`
   - `backers_count`
   - `country`
   - `currency`
   - `launch_date` (formerly `launched_at`, in datetime format)
   - `end_date` (formerly `deadline`, in datetime format)
   - `category_id` (matching `category_id` in the category DataFrame)
   - `subcategory_id` (matching `subcategory_id` in the subcategory DataFrame)
3. Export the campaign DataFrame as `campaign.csv` and save it to the repository.

### 3. Create the Contacts DataFrame

Choose one of the two options to extract and transform the data from `contacts.xlsx`:

#### Option 1: Using Python Dictionary Methods

1. Import the `contacts.xlsx` file into a DataFrame.
2. Iterate through the DataFrame, converting each row to a dictionary.
3. Extract dictionary values using list comprehensions.
4. Create a new DataFrame with the extracted data.
5. Split the `name` column into `first_name` and `last_name`.
6. Clean and export the DataFrame as `contacts.csv`.

#### Option 2: Using Regular Expressions

1. Import the `contacts.xlsx` file into a DataFrame.
2. Extract the `contact_id`, `name`, and `email` columns using regular expressions.
3. Create a new DataFrame with the extracted data.
4. Convert the `contact_id` column to the integer type.
5. Split the `name` column into `first_name` and `last_name`.
6. Clean and export the DataFrame as `contacts.csv`.

### 4. Create the Crowdfunding Database

1. Inspect the four CSV files and create an ERD using QuickDBD.
2. Create a table schema based on the ERD and save it as `crowdfunding_db_schema.sql`.
3. Create a new Postgres database named `crowdfunding_db`.
4. Using the schema, create tables in the correct order to handle foreign keys.
5. Verify the table creation with SELECT statements.
6. Import each CSV file into its corresponding SQL table.
7. Verify the data in each table with SELECT statements.

## Requirements

- **Category DataFrame:**
  - `category_id` column with sequential entries from "cat1" to "catn".
  - `category` column with category titles.
  - Exported as `category.csv`.

- **Subcategory DataFrame:**
  - `subcategory_id` column with sequential entries from "subcat1" to "subcatn".
  - `subcategory` column with subcategory titles.
  - Exported as `subcategory.csv`.

- **Campaign DataFrame:**
  - Columns as specified in the instructions.
  - Exported as `campaign.csv`.

- **Contacts DataFrame:**
  - `contact_id`, `first_name`, `last_name`, and `email` columns.
  - Exported as `contacts.csv`.

- **Crowdfunding Database:**
  - Database schema `crowdfunding_db_schema.sql`.
  - Database `crowdfunding_db` created and populated with data from CSV files.
  - Data verification with SELECT statements.
