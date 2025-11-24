# YouTube Data Extraction & Analysis

## Overview

This project focuses on extracting, analyzing, and processing data from **YouTube** using the **YouTube Data API v3**. The workflow covers API setup, data retrieval for a chosen search query, video-level statistical analysis, comment extraction, structured data export, and computation of engagement metrics. The outcome is a complete, programmatic pipeline for understanding video performance and audience interaction on the platform.

---

## API Setup

### Creating the API Key (The entire process with pictures and screenshots are available in the said .ipynb file)

A YouTube API key was created through the **Google Cloud Console**.
The key steps included:

* Opening the Google Cloud Console and creating a new project.
* Naming the project (**PranalYoutube**) and configuring organization settings.
* Navigating to **APIs and Services → Library**.
* Enabling **YouTube Data API v3**.
* Creating an API key through **APIs and Services → Credentials**.
* Retaining the generated key for authenticated API requests.

### Installing Required Libraries

* Installed the **Google API Python client** to enable authorized programmatic access to YouTube’s data endpoints.

---

## Data Retrieval

### Search Query

A search request was executed for the query string:
**“avatar movie”**

The search was configured to:

* Retrieve the **top 50** results
* Sort results by **relevance**
* Restrict responses to the **US region**

### Video Statistics

For each retrieved video, relevant metadata and statistics were extracted, including:

* Video ID
* Title
* Views
* Likes
* Comments
* Additional YouTube statistics fields

These were exported to a CSV file (`video_stats.csv`) for further analysis.

---

## Data Analysis

### Top Commented Videos

The dataset was sorted by **comment count**, and the top **10 most-commented videos** were identified.
The extracted attributes included:

* Video ID
* Video Title
* Total Comment Count

### Comment Extraction

A dedicated method was used to retrieve **comments** for each of the top 10 videos.
All comments pulled from the API were exported to a structured JSON file (`comments_output.json`).

### Engagement Metric

A function was implemented to compute the **likes-to-views ratio** for any video in the dataset, enabling quick comparison of engagement levels across videos.

---

## File Outputs

All generated files can be found in the project’s file directory:

* **video_stats.csv** — Contains statistics for the top 50 search results
* **comments_output.json** — Contains extracted comments for the top 10 most-commented videos

Accessible via the environment’s **Table of Contents → Files** section.

---

## Purpose

This project demonstrates a complete end-to-end workflow for interacting with the YouTube Data API:

* API configuration
* Data extraction at scale
* Statistical analysis of public video metrics
* Comment harvesting for deeper insight
* Export of structured datasets for further processing

The resulting pipeline provides a foundational framework for analyzing content trends, audience sentiment, and engagement dynamics on YouTube.

