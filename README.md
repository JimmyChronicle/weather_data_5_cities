# Weather Data ETL Pipeline

## Project Overview
This project builds a basic **ETL (Extract, Transform, Load)** pipeline that collects real-time weather data from the OpenWeatherMap API, cleans and structures the data using Python, stores it in multiple formats, and performs simple analysis.  

The goal is to demonstrate how to extract data from an external API, process it into a usable format, and prepare it for analysis.

## Data Source
- **API**: OpenWeatherMap API  
- **Website**: [https://openweathermap.org/api](https://openweathermap.org/api)  
- **Endpoint Used**: Current Weather Data (`/data/2.5/weather`)  
- **Cities Selected**: Lagos, Nairobi, Cairo, Johannesburg, Accra  

## ETL Process

### 1. Extract
- Connected to the OpenWeatherMap API using a free API key.
- Retrieved current weather data for 5 African cities.
- Extracted the following fields:
  - City Name
  - Country
  - Temperature (°C)
  - Humidity (%)
  - Weather Condition
  - Wind Speed (m/s)
  - Date & Time (UTC)

### 2. Transform
- Converted the raw JSON responses into a structured **Pandas DataFrame**.
- Renamed columns for better readability.
- Converted data types (temperature, humidity, and wind speed to numeric).
- Standardized weather condition text (title case).
- Created a clean dataset ready for analysis.

### 3. Load
The cleaned data was stored in three different formats for future use:
- **CSV** → `weather_data.csv`
- **Excel** → `weather_data.xlsx`
- **SQLite Database** → `weather_data.db` (table name: `weather`)

## Tools Used
- **Python**
- **Requests** – for making API calls
- **Pandas** – for data transformation and analysis
- **SQLite3** – for database storage
- **OpenPyXL** – for saving Excel files
- **OpenWeatherMap API**

## Steps Taken
1. Created a free account on OpenWeatherMap and generated an API key.
2. Wrote a Python script to extract weather data for five cities.
3. Transformed the raw data into a clean Pandas DataFrame.
4. Saved the cleaned data in CSV, Excel, and SQLite formats.
5. Performed basic analysis:
   - Compared temperatures across cities
   - Identified the city with the highest humidity
   - Compared weather conditions
6. Documented the entire process in this README file.

## Key Findings
- The hottest city among the selected cities was identified based on current temperature.
- The city with the highest humidity was clearly determined.
- Weather conditions varied across the cities (e.g., Clear Sky, Clouds, Rain, etc.).
- The ETL pipeline successfully extracted, cleaned, and stored the data for future analysis.

## How to Run the Project
1. Install the required libraries:
   ```bash
   pip install requests pandas openpyxl
