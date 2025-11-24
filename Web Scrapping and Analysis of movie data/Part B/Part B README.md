# Movie Data Web Scraping & Database Construction (TMDB)

## Overview

This project focuses on building a structured movie dataset by scraping information from **The Movie Database (TMDB)**. The workflow includes retrieving HTML content, parsing movie listings, extracting relevant attributes, and assembling multi-page data into a consolidated DataFrame. The goal is to create a clean, analyzable dataset containing titles, ratings, genres, cast lists, and raw HTML blocks for each movie.

## Web Scraping Workflow

### 1. Connecting to TMDB

A connection was established to the TMDB movie listings page (`https://www.themoviedb.org/movie`) using an HTTP GET request.

* The `requests` library was used to download webpage content.
* Status codes were checked to confirm successful retrieval.
* Raw HTML responses were printed and stored for further processing.
* The data type of the downloaded content was verified, and the initial characters of the response were inspected for validation.

### 2. Parsing HTML with BeautifulSoup

The downloaded HTML content was parsed with **BeautifulSoup** for structured access to webpage elements.

* A BeautifulSoup object was created from the raw HTML.
* The page title was extracted.
* A reusable function was implemented to accept any URL, verify request validity, raise exceptions for errors, and return a BeautifulSoup instance.
* Test cases included one valid URL and one URL returning a 404 response.

### 3. Extracting Movie-Specific Information

Using the parsed TMDB listings page:

* The first movie’s full HTML listing block was identified and printed.
* The movie title, user rating, and URL fragment were extracted.
* The substring extraction for URL paths avoided use of built-in string manipulation functions and relied solely on HTML element structure.

### 4. Extracting Data for All Movies on the Page

Full lists of attributes were collected for every movie on the listing page:

* **Titles**
* **User Ratings**
* **Full HTML blocks for each movie’s individual page**
* **Genres**
* **Cast Lists**

These elements were gathered using specific HTML selectors for each target attribute.

### 5. Assembling a Structured DataFrame

A user-defined function was created to compile the scraped movie information into a unified **pandas DataFrame** containing:

* Movie Titles
* User Ratings
* Genres
* Cast Lists

The DataFrame provides a clean, analysis-ready representation of the scraped attributes.

### 6. Multi-Page Scraping & Consolidation

A dedicated function was developed to scrape TMDB pages **1 through 5**:

* For each page, the scraping utilities handled page retrieval, movie-level HTML extraction, and DataFrame assembly.
* Five DataFrames (one per page) were generated and made export-ready.
* These DataFrames were then merged into a **single, combined dataset** containing all movies scraped across the first five TMDB pages.

## Output

* Individual DataFrames for pages 1–5
* A fully merged DataFrame containing all collected movie data
* CSV-export-ready datasets
* Parsed HTML structures for further processing or analysis

## Purpose

This project demonstrates end-to-end web scraping, HTML parsing, structured data extraction, multi-page aggregation, and DataFrame construction for building a scalable movie information database sourced from TMDB.

