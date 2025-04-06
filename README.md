# Daily Weather & Bible Verse Webpage

This simple webpage displays the current weather information for Ottawa, Ontario, Canada, along with an hourly forecast for the next few hours and a daily Bible verse.

## Features

* **Current Weather:** Shows the current temperature, conditions, and wind speed for Ottawa, ON.
* **Feels Like Temperature:** Displays the apparent temperature, providing a better sense of how the weather feels.
* **Weather Advice:** Offers a short, context-aware message like "Dress warmly" or "Don't forget your umbrella" based on the current conditions.
* **Hourly Forecast:** Presents a minimal forecast for the next 6 hours, including the time, weather icon, and temperature.
* **Daily Bible Verse:** Fetches and displays a random Bible verse along with its reference.
* **Live Clock:** Shows the current day, date, and time, updating in real-time.
* **Responsive Design:** Layout adapts to different screen sizes.
* **Minimalist Themed Icons:** Uses Font Awesome icons for a clean and thematic visual style.

## Technologies Used

* HTML
* CSS
* JavaScript
* [Font Awesome](https://fontawesome.com/) for icons.
* [Open-Meteo API](https://open-meteo.com/) for weather data (no API key required).
* [OurManna API](https://beta.ourmanna.com/) for the daily Bible verse (no API key required).

## Setup

To run this webpage locally, you only need a web browser:

1.  **Save the Code:** Save the provided HTML code as an `.html` file (e.g., `weather_bible.html`).
2.  **Open in Browser:** Open the saved HTML file in your web browser (Chrome, Firefox, Safari, etc.).

The webpage will automatically fetch the weather data and Bible verse from the respective APIs and update the displayed information.

## Configuration

* **Location:** The weather data is currently set to fetch information for Ottawa, Ontario, Canada (latitude: 45.3041, longitude: -75.9058). To change the location, you need to modify the `latitude` and `longitude` parameters in the `fetch` request URL within the `<script>` section of the HTML file. You can find these coordinates for other locations using online map services.

    ```javascript
    fetch("[https://api.open-meteo.com/v1/forecast?latitude=YOUR_LATITUDE&longitude=YOUR_LONGITUDE&current_weather=true&hourly=temperature_2m,apparent_temperature,weathercode,windspeed_10m](https://www.google.com/search?q=https://api.open-meteo.com/v1/forecast%3Flatitude%3DYOUR_LATITUDE%26longitude%3DYOUR_LONGITUDE%26current_weather%3Dtrue%26hourly%3Dtemperature_2m,apparent_temperature,weathercode,windspeed_10m)")
    ```

* **Weather Advice:** The text displayed by the "weather advice" feature can be customized by modifying the conditions and messages within the `getWeatherAdvice` JavaScript function.

    ```javascript
    function getWeatherAdvice(temperature, weatherCode) {
        if (temperature < 10) {
            return "Looks chilly! Dress warmly.";
        } else if (weatherCode >= 51 && weatherCode <= 67) { // Rain or Freezing Rain
            return "Don't forget your umbrella!";
        }
        // ... other conditions
        return "";
    }
    ```

## Credits

* Weather data provided by the [Open-Meteo API](https://open-meteo.com/) (no API key required).
* Bible verse provided by the [OurManna API](https://beta.ourmanna.com/) (no API key required).
* Icons provided by [Font Awesome](https://fontawesome.com/).
* Written with help from ChatGPT and Gemini.

## License

This project is open-source and available under the [MIT License](LICENSE)
