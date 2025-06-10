# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a single-page web application that scrapes Steam game reviews and exports them to Excel files. The entire application is contained within `index.html` - a self-contained HTML file with embedded CSS and JavaScript.

## Architecture

- **Frontend**: Vanilla HTML/CSS/JavaScript with no build process
- **External Dependencies**: 
  - XLSX library (via CDN) for Excel file generation
  - AllOrigins proxy service for CORS bypass
- **APIs Used**:
  - Steam Store API for game search and review data
  - SteamSpy API for top games list
  - AllOrigins proxy service for cross-origin requests

## Key Components

- **Game Search**: Uses Steam Store API to search for games
- **Game Display**: Grid-based layout showing game tiles with images
- **Review Scraping**: Paginated scraping of Steam reviews with rate limiting
- **Data Export**: Converts scraped reviews to Excel format using XLSX library
- **Context Menu**: Right-click or left-click interface for game actions

## Development Notes

- No build process required - open `index.html` directly in browser
- Uses modern JavaScript features (async/await, fetch, template literals)
- Implements proper rate limiting (1 second delays) to avoid Steam API throttling
- Handles CORS issues via AllOrigins proxy service
- All styles are embedded in `<style>` tags within the HTML
- Uses dark theme styling throughout

## Data Flow

1. Load top games from SteamSpy API on page load
2. Allow user search via Steam Store API
3. Display games in grid format with hover effects
4. Context menu allows scraping reviews or opening store page
5. Review scraping uses cursor-based pagination
6. Export scraped data as Excel file for download