# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a "pizzaSpider" project - a cyberpunk-themed interactive map visualization that creates dynamic hub-and-spoke maps showing pizza locations with animated "tentacle" connections. The application uses real-time geolocation and live API data to find nearby pizzerias.

## Architecture

- **Single HTML file**: `index.html` contains all HTML, CSS, and JavaScript in one file
- **Data directory**: Contains legacy GeoJSON files (not currently used in main functionality)
- **Client-side only**: Pure frontend application with no build process or server requirements
- **Real-time data**: Uses OpenStreetMap Overpass API for live pizza location data

## Key Components

- **Map visualization**: Mapbox GL JS v2.9.0-beta.2 with dark cyberpunk theme
- **Geospatial calculations**: Turf.js for distance calculations and nearest point finding
- **Data loading**: D3.js v4 (loaded but primarily for legacy compatibility)
- **Real-time location**: Browser geolocation API with fallback to Quito coordinates
- **Cyberpunk UI**: Custom HUD overlay with scan lines, status bars, and animated elements
- **Core algorithm**: Finds 10 nearest pizza locations to current map center and draws animated connecting lines

## Data Flow

1. **Location acquisition**: Uses `navigator.geolocation` to get user's current position
2. **API queries**: Calls OpenStreetMap Overpass API to search for pizzerias within 25km radius
3. **Data processing**: Converts Overpass response to GeoJSON format with standardized properties
4. **Visualization**: Creates animated tentacle-like connections between user location and nearest 10 pizzerias
5. **Dynamic updates**: Refreshes data when user moves map center by more than 5km

## Development Commands

- **Local development**: Open `index.html` directly in browser or serve via HTTP server
- **Testing location**: Use browser dev tools to simulate different geographic locations
- **API debugging**: Monitor Network tab for Overpass API calls (overpass-api.de)

## Key Implementation Details

- **Overpass query**: Searches for `amenity=restaurant` with `cuisine~pizza` and `shop=pizza`
- **Geolocation fallback**: Falls back to Quito, Ecuador (-78.4678, -0.1807) if location unavailable
- **Animation system**: Custom tentacle animation with 20-step interpolation using `easeInOutSine`
- **Update threshold**: Only refreshes pizza data when map moves >5km (approximately 5 minutes driving)
- **Unique identifiers**: Uses `OSM${element.id}` format for `shopCode` property
- **Color cycling**: Lines and points cycle through cyan (#00FFFF), magenta (#FF00FF), and yellow (#FFFF00)

## API Configuration

- **Mapbox access token**: Hardcoded in line 257 (ajrae account)
- **Map style**: Uses `mapbox://styles/mapbox/dark-v11` for cyberpunk aesthetic
- **Overpass API**: Uses public instance at `https://overpass-api.de/api/interpreter`
- **No API keys needed**: OpenStreetMap Overpass API is free and doesn't require authentication

## Cyberpunk UI Elements

- **HUD overlay**: Corner frames, status bars, coordinates display, timestamp
- **Data stream**: Simulated terminal output with random color cycling
- **Scan lines**: Animated scan effect across entire viewport
- **Tooltips**: Custom cyberpunk-styled popups with distance and travel time calculations
- **Glitch effects**: Random glitch animations triggered on hover events
- **Mobile responsive**: Collapsible data stream with floating toggle button for mobile devices

## Mobile Adaptations

- **Responsive breakpoint**: 600px max-width triggers mobile layout
- **UI simplifications**: Corner frames hidden, smaller fonts, adjusted positioning
- **Data stream**: Collapsible panel with floating toggle button (☰) for mobile users
- **Touch optimization**: Adjusted element sizes and spacing for touch interfaces
- **Full viewport**: Map takes full screen real estate on mobile devices