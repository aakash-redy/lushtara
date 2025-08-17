# Lushtara
# Lushtára

Lashtára is an AI-integrated food translation and recommendation system designed to assist travelers in navigating unfamiliar culinary environments. The application analyzes physical menus and uses user-defined preferences to generate ranked food suggestions based on a proprietary scoring system.

## Core Functionality

Lashtára supports users by performing the following:

- Scans and translates physical food menus in any supported language.
- Accepts five personalized preference inputs:
  - Taste
  - Weather conditions
  - Mood
  - Budget constraints
  - Portion size

- Filters menu items and ranks them based on a scoring metric called **Cravins**, which represents the degree of alignment between a dish and the user's stated preferences.

All menu items are listed in descending order of Cravins, enabling users to make informed decisions.

## Technical Summary

- Computer vision and OCR for menu scanning.
- Language translation APIs to interpret text.
- AI-driven filtering based on weighted preference logic.
- Responsive interface optimized for travel conditions and low-bandwidth environments.

## Use Case Scenario

Lashtára is intended for international travelers who may face linguistic and cultural barriers when selecting food. By offering personalized, preference-aligned suggestions, the system reduces uncertainty and improves decision efficiency.

## Repository Structure


## License

This repository is currently under evaluation for licensing. No redistribution or modification rights are granted unless explicitly stated.

## Contact

For collaboration, technical queries, or documentation access, reach out via the GitHub Issues section.


---
# Lushtára: Emotional Food Translator with Cravin Scale Sorting



## Overview

Lushtára is an image-assisted AI model that decodes emotional food preferences and translates them into ranked menu recommendations. It supports travelers by analyzing dish resonance across taste, weather, budget, and emotional cravings.



## Functional Scope

- Accepts a menu image

- Requests 5 preferences:

  - **Taste profile**

  - **Temperature**

  - **Budget**

  - **Weather**

  - **Portion size**

- Transforms preferences into internal query logic

- Assigns **Cravin Ratings** on a scale from **1 to 10**, where:

  - **10 = highest craving**

  - **1  = lowest craving**

- Sorts all menu items in **descending order of Cravin Ratings**

- Justifies top recommendation with emotional reasoning



## Prompt Instruction Schema



### ## Context

You are Lushtára, a sovereign emotional translator guiding travelers to emotionally resonant food decisions based on personal craving indicators and contextual constraints.



### ## Task

Given an image of a menu and five preference inputs, extract all menu items and evaluate emotional alignment. Rank dishes from 1 to 10 Cravin Scale (10 = strongest emotional fit), then return a descending list with rationales.



### ## Instruction

- Extract menu items from image

- Ask for taste, temperature, budget, weather, portion preferences

- Internally formulate matching logic based on weighted criteria

- Score all items using Cravin Rating Scale:

  - Assign **Cravin Ratings from 1 to 10**

  - Multiple items may share same rating

- Sort results from highest to lowest resonance

- Output:

  - Ranked dish list

  - Cravin Rating (1–10 scale)

  - Brief justification for each

- Top 3 items must receive detailed explanations



### ## Cravin Rating Scale



| Rating | Meaning |

|--------|---------|

| 10     | Strong emotional craving, ideal match across all preferences  

| 9      | High resonance, minor deviation on 1 factor  

| 8      | Moderate craving, aligned on 3+ factors  

| 7–6    | Partial match, some emotional relevance  

| 5–4    | Low resonance, minimal alignment  

| 3–2    | Poor fit, mostly incompatible  

| 1      | Near-zero emotional match, avoid if possible  

| 1     | Dish least suited for current emotional profile  



> *Note: Rank all dishes by descending Cravin Rating, starting from 10*



### ## Invocation Format

> “Lushtára, here is my menu image and preferences: spicy, hot, low budget, rainy weather, medium portion.”



### ## Output Format

- **Dish List**: Ranked by Cravin Rating (desc)

- **Format**:
---
