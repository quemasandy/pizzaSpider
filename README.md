# 🍕 Pizza Finder Cyberpunk

A futuristic, cyberpunk-themed web app to help you find the nearest pizzerias in your city, visualized on an interactive map with animated "tentacle" connections and a stylish HUD overlay.

## 🚀 What does this project do?

**Pizza Finder Cyberpunk** is a web application that:
- Uses your current location (or a default city) to search for nearby pizzerias using the OpenStreetMap Overpass API.
- Displays the 10 closest pizza places on a Mapbox GL JS map.
- Animates glowing lines ("tentacles") from your location to each pizzeria, creating a unique cyberpunk effect.
- Shows a futuristic HUD overlay with real-time GPS coordinates, UTC time, and a data stream.
- Provides interactive tooltips with distance and estimated travel time (walking/driving) to each pizzeria.
- All in a fully static, client-side app—no backend required!

## 🗺️ Technologies Used

- [Mapbox GL JS](https://docs.mapbox.com/mapbox-gl-js/) for interactive mapping
- [Turf.js](https://turfjs.org/) for geospatial calculations
- [OpenStreetMap Overpass API](https://overpass-api.de/) for real-time pizza place data
- [D3.js](https://d3js.org/) for potential data visualizations
- Pure HTML, CSS (with cyberpunk style), and JavaScript

## 🌍 How to Use

1. Open the app in your browser or visit [https://quemasandy.github.io/pizzaSpider/](https://quemasandy.github.io/pizzaSpider/)
2. Allow location access for the best experience.
3. Watch as the map centers on your position and animates the nearest pizzerias.
4. Hover over any glowing point to see details and estimated travel times.

## 📦 Deployment

This project is fully static and can be deployed on [GitHub Pages](https://pages.github.com/), Netlify, Vercel, or any static hosting provider.

## 🙏 Credits

- **Mapbox** for the mapping platform.
- **OpenStreetMap** for open geodata.
- **Turf.js** and **D3.js** for geospatial and visualization tools.
- **Cyberpunk HUD inspiration** from various open-source projects.
- **Special thanks to [Alasdair Rae (@alasdairrae)](https://github.com/alasdairrae)** for geodata inspiration and open mapping resources.

---

> This project is open source and welcomes contributions!
