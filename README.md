# Weather Data API

A Flask-based RESTful API that provides historical temperature data for various weather stations. The project allows users to query temperature data by station ID, specific dates, and yearly records.

## Features

- View all available weather stations
- Get temperature data for a specific station on a specific date
- Retrieve all temperature records for a specific station
- Get yearly temperature data for a specific station

## Technologies Used

- Python 3.x
- Flask (Web Framework)
- Pandas (Data Processing)
- HTML (Frontend)

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd weather-api
```

2. Create and activate a virtual environment:
```bash
python -m venv .venv
# On Windows
.venv\Scripts\activate
# On Unix or MacOS
source .venv/bin/activate
```

3. Install the required dependencies:
```bash
pip install flask pandas
```

## Project Structure

```
weather-api/
├── main.py              # Main application file
├── data_small/          # Directory containing weather station data
│   └── stations.txt     # List of weather stations
│   └── TG_STAID*.txt   # Temperature data files
├── templates/           # HTML templates
│   └── home.html       # Homepage template
└── static/             # Static files (CSS, JS, etc.)
```

## API Endpoints

1. Homepage
   - URL: `/`
   - Method: `GET`
   - Description: Displays the list of all available weather stations

2. Get Temperature for Specific Station and Date
   - URL: `/api/v1/<station>/<date>`
   - Method: `GET`
   - Parameters:
     - station: Station ID
     - date: Date in YYYY-MM-DD format
   - Returns: JSON with station ID, date, and temperature

3. Get All Data for a Station
   - URL: `/api/v1/<station>`
   - Method: `GET`
   - Parameters:
     - station: Station ID
   - Returns: JSON array with all temperature records

4. Get Yearly Data for a Station
   - URL: `/api/v1/yearly/<station>/<year>`
   - Method: `GET`
   - Parameters:
     - station: Station ID
     - year: Year in YYYY format
   - Returns: JSON array with temperature records for the specified year

## Example Usage

1. Get temperature for station 10 on October 25, 1988:
```
http://127.0.0.1:5000/api/v1/10/1988-10-25
```

2. Get all temperature records for station 10:
```
http://127.0.0.1:5000/api/v1/10
```

3. Get temperature records for station 10 in 1988:
```
http://127.0.0.1:5000/api/v1/yearly/10/1988
```

## Running the Application

1. Activate the virtual environment (if not already activated)
2. Run the application:
```bash
python main.py
```
3. Open a web browser and navigate to `http://127.0.0.1:5000`

## Data Format

The temperature data is stored in text files with the following format:
- Temperature values are stored in tenths of a degree Celsius
- The API automatically converts the values to actual degrees Celsius when serving the data
- Dates are in YYYY-MM-DD format

## Contributing

Feel free to submit issues and enhancement requests! 