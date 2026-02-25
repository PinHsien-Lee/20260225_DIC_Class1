# LEE Personal Website

## Overview
This is a single-page personal website featuring a modern, premium **glassmorphism** design. It serves as a personal dashboard that displays the user's name, the real-time clock and date, their current geographic location, and local weather via dynamic API calls.

## Technologies Used
- **HTML5**: Semantic structure.
- **Vanilla CSS**: Used for layout, typography, animations, and the glassmorphism effects without relying on external libraries (like Tailwind).
- **Vanilla JavaScript**: Handles the live clock logic, handles API requests for location and weather data, and dynamically generates background particle animations.

## Key Features

### 1. **Visual Design & Animations**
- **Animated Background**: A gradient background that shifts continuously, overlaid with floating blurry color orbs and twinkling "star" particles added dynamically via JavaScript.
- **Glassmorphism Card**: The main content area sits inside a centered, semi-transparent frosted-glass card with a stylized glowing hover border effect.
- **Custom Typography**: Integrates Google Fonts (`Outfit`, `Space Mono`) and the custom **Huninn** font for displaying the name "**LEE**" and the footer tagline "**我想下課**".
- **Dynamic Gradient Text**: The name "LEE" utilizes background-clip text with a moving gradient.

### 2. **Real-time Clock**
- JavaScript interval updates the clock (`HH:MM:SS`) and standard time formatting every single second.
- The date string automatically maps the current day of the week and month to a fully readable format (e.g., *Wednesday, 25 February 2026*).

### 3. **Geolocation & Weather Integration**
Provides accurate environmental context by querying third-party APIs:
- **Location Permission Prompt**: Utilizes the browser's native `navigator.geolocation` API to ask the user for permission to use their exact coordinates.
- **Reverse Geocoding**: If permission is granted, it sends the coordinates to the `BigDataCloud` API to retrieve the user's City and Country.
- **IP Location Fallback**: If the user denies location permission, times out, or blocks the prompt, the application gracefully falls back to querying `ipapi.co` to estimate location via their IP address.
- **Open-Meteo Weather**: Passes the retrieved latitude and longitude coordinates into the `open-meteo.com` API to display the real-time local temperature in Celsius.
