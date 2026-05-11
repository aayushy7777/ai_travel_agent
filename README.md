# AI_TRAVEL_AGENT

#python code

# 🌦️ Weather App using OpenWeather API

A simple Python project that fetches real-time weather data using the OpenWeatherMap API.

---

## 📌 Features

- Get current weather by city name
- Displays:
  - Weather description
  - Temperature in Celsius
- Uses OpenWeatherMap API
- Simple and beginner-friendly Python code

---

## 🛠️ Tech Stack

- Python
- Requests Library
- OpenWeatherMap API

---

## 📂 Project Structure

```bash
weather-app/
│── main.py
│── README.md
```

---

## 🚀 Installation

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/weather-app.git
cd weather-app
```

---

### 2️⃣ Install Dependencies

```bash
pip install requests
```

---

### 3️⃣ Get API Key

- Visit: https://openweathermap.org/api
- Create a free account
- Generate your API key

---

### 4️⃣ Add Your API Key

Replace:

```python
API_KEY = "PASTE_YOUR_API_KEY_HERE"
```

with:

```python
API_KEY = "your_actual_api_key"
```

---

# 📜 Python Code

```python
import requests

API_KEY = "PASTE_YOUR_API_KEY_HERE"

def main(location: str) -> str:
    base_url = "http://api.openweathermap.org/data/2.5/weather"
    
    params = {
        "q": location,
        "appid": API_KEY,
        "units": "metric",
    }

    response = requests.get(base_url, params=params)
    data = response.json()

    if response.status_code == 200:
        weather_desc = data["weather"][0]["description"]
        temp = data["main"]["temp"]

        return {
            "result": f"Current weather in {location}: {weather_desc}, Temperature: {temp}°C"
        }

    else:
        return {
            "result": "Could not retrieve weather data",
        }

# Example Usage
print(main("Mumbai"))
```

---

# ▶️ Example Output

```bash
Current weather in Mumbai: scattered clouds, Temperature: 31°C
```

---

# ❌ Error Handling

If the city name is invalid or API fails:

```bash
Could not retrieve weather data
```

---

# 📚 API Reference

### Endpoint Used

```bash
http://api.openweathermap.org/data/2.5/weather
```

### Parameters

| Parameter | Description |
|-----------|-------------|
| `q` | City Name |
| `appid` | API Key |
| `units` | Temperature Unit (`metric`) |

---

# 🔥 Future Improvements

- Add humidity and wind speed
- Add weather icons
- Create GUI using Tkinter
- Deploy as web app using Flask/Streamlit
- Add 5-day weather forecast

---

# 👨‍💻 Author

Developed using Python and OpenWeatherMap API.
