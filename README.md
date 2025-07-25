# lushtara
# Lashtára

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

## Cravins Scoring System

Each dish receives a **Cravins** score ranging from +5 to -5:

- **+5** indicates highest resonance with user preferences.
- **0** represents neutral or moderate match.
- **-5** reflects least alignment.

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
