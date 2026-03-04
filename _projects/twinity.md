---
layout: page
title: Twinity
description: A digital twin for trail running — analysing FIT files from GPS watches to model fitness, fatigue, and performance readiness using the Banister system model.
importance: 1
category: fun
related_publications: false
---

## Overview

**Twinity** is a personal project aimed at building a **digital twin of a trail runner**,
combining physiological data, training load models, and field performance metrics to
simulate and optimise endurance training.

The system ingests `.FIT` files from GPS sports watches (Suunto, Garmin, etc.) to
reconstruct training sessions and provide insights into **fitness**, **fatigue**, and
**performance readiness** — with the long-term goal of personalising the model using
machine learning.

Because why apply data science only to Mars when you can also apply it to mountains? 🏔️

## Features

**Data ingestion**  — recursive loading of `.FIT` files, extraction of distance,
elevation, pace, heart rate, and power; structured storage in a local SQLite database.

**Session management** — edit, annotate, and delete sessions; add metadata such as
sport type, RPE (Rate of Perceived Exertion), and free-text notes.

**Performance analytics** — heart rate zones, training load computation, intensity
distributions, session-level dashboards with bar plots and time-in-zone histograms.

**Training load modelling** — fitness–fatigue dynamics using the
[Banister impulse–response model](https://doi.org/10.1007/BF00697919),
enabling predictive simulations of race-day readiness and recovery time.

**Streamlit interface** — interactive dashboard with tabs for athlete selection,
session listing, session analytics, and global performance trends.

## Technical Details

- **Language:** Python / Jupyter Notebook
- **Interface:** [Streamlit](https://streamlit.io)
- **Key dependencies:** `fitparse`, `pandas`, `numpy`, `matplotlib`, `scikit-learn`
- **Storage:** local SQLite database (auto-created on first run)
- **Status:** active development

## Usage

```bash
# Install dependencies
conda env create -f environment.yml
conda activate twinity

# Run the dashboard
streamlit run app.py
```

Then load your `.FIT` files from the interface — sessions are parsed automatically
and stored locally.

## Links

- [GitHub repository](https://github.com/GregS1t/Twinity)