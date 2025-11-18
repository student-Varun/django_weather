🌦️ Weather App — Real-Time Weather Forecast (Django)

A dynamic Real-Time Weather Application built using Django, OpenWeather API, and Google Custom Search Engine API to display accurate weather information along with high-quality images of the searched city.

This project demonstrates API integration, backend logic, and dynamic data rendering in Django.

🚀 Features

🌤 Real-Time Weather Data
Fetches live data (temperature, humidity, pressure, description, etc.) from OpenWeatherMap API.

🏙️ City Image Display
Integrates Google Programmable Search Engine API to show a relevant image of the searched city.

🔍 Search Any City in the World
Enter any city name and instantly get weather + image results.

🛠 Django-Powered Backend
Clean and scalable Django project structure with proper routing and views.

📡 API Integration
Demonstrates how to consume multiple external APIs inside a Django app.

📱 Responsive UI (if applicable)
Works smoothly on desktop and mobile.

🖼️ Demo

(Add screenshots here)
Example:

/screenshots/home.png
/screenshots/search.png

📂 Project Structure
Weather-App/
│
├── weatherproject/            # Main project settings
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
│
├── weatherapp/                # Main application
│   ├── views.py               # API calls + business logic
│   ├── urls.py
│   ├── templates/             # HTML templates
│   ├── static/                # CSS / images
│   └── models.py
│
├── manage.py
└── README.md

🔑 API Keys Required
1. OpenWeatherMap API

Used to fetch real-time temperature & weather details.
👉 https://openweathermap.org/api

2. Google Custom Search Engine (CSE) API

Used to fetch city images.
👉 https://programmablesearchengine.google.com/

Add both keys inside your Django view:
WEATHER_API = "YOUR_OPENWEATHER_API_KEY"
SEARCH_ENGINE_ID = "YOUR_GOOGLE_CSE_ID"
GOOGLE_API_KEY = "YOUR_GOOGLE_API_KEY"

⚙️ Installation & Setup
📌 1. Clone the repository
git clone https://github.com/yourusername/weather-app.git
cd weather-app

📌 2. Create a virtual environment
python -m venv venv
venv\Scripts\activate       # Windows
source venv/bin/activate   # Mac/Linux

📌 3. Install dependencies
pip install -r requirements.txt

📌 4. Add your API keys

Inside views.py or .env file.

📌 5. Run the server
python manage.py runserver


Visit:
👉 http://127.0.0.1:8000/

📡 How It Works
⭐ Weather API Call

Example:

weather_url = "https://api.openweathermap.org/data/2.5/weather"
params = {
    "q": city,
    "appid": WEATHER_API,
    "units": "metric"
}
weather_data = requests.get(weather_url, params=params).json()

⭐ Google Image Search API Call
google_url = "https://www.googleapis.com/customsearch/v1"
params = {
    "key": GOOGLE_API_KEY,
    "cx": SEARCH_ENGINE_ID,
    "q": city,
    "searchType": "image",
    "imgSize": "large"
}
image_data = requests.get(google_url, params=params).json()


Both responses are combined and displayed on the frontend.

🧪 Example Output

City Name

Temperature (°C)

Humidity

Weather Description

City Image

Date / Time

“Feels Like” temperature

🧰 Technologies Used

Python 3

Django 4+

OpenWeather API

Google Custom Search API

HTML / CSS / JS

Requests Library

📌 Future Enhancements

🌍 Add weekly weather forecast

📍 Auto-detect user location

🎨 Improve UI/UX

📱 Add mobile-friendly React frontend

🌫 Air quality details (AQI API)

🤝 Contributing

Feel free to submit pull requests or open issues to improve the project.

📜 License

This project is licensed under the MIT License.

🙌 Acknowledgements

OpenWeatherMap for weather data

Google CSE for image results

Django for powerful backend support