# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a "pizzaSpider" project - an interactive map visualization that creates dynamic hub-and-spoke maps using Turf.js and Mapbox. The project was originally built for Greggs locations but has been adapted to show Quito pizzerias.

## Architecture

- **Single HTML file**: `index.html` contains all the HTML, CSS, and JavaScript
- **Data directory**: Contains GeoJSON files with location data for mapping
- **Client-side only**: Pure frontend application with no build process or server requirements

## Key Components

- **Map visualization**: Uses Mapbox GL JS v2.9.0-beta.2 for rendering
- **Geospatial calculations**: Turf.js for finding nearest points and creating line features
- **Data loading**: D3.js v4 for loading GeoJSON data
- **Core algorithm**: Finds 10 nearest locations to the current map center and draws connecting lines

## Data Structure

The GeoJSON files in `/data/` must follow this structure:
- Each feature requires a unique `shopCode` property (referenced in line 81 of index.html)
- Features should have `name`, `address`, and `type` properties for display
- Coordinates should be in [longitude, latitude] format

## Development Notes

- **No build process**: Simply open `index.html` in a browser or serve via HTTP server
- **Data updates**: Replace GeoJSON files in `/data/` directory and update the filename reference in index.html line 36
- **Map configuration**: Mapbox access token is hardcoded (line 22), uses MapTiler style (line 25)
- **Center point**: Currently configured for Quito, Ecuador coordinates (line 26)
- **Unique identifier**: When adapting for new datasets, ensure the `shopCode` property name matches the reference in line 81

## API Keys

The project uses:
- Mapbox access token (currently exposed in code)
- MapTiler API key for map styles (currently exposed in code)