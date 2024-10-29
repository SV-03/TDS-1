# TDS-1
Austin Users and Repositories

- Data was scraped from the GitHub API based on users in Austin with over 100 followers and includes their public repositories.
- Interesting finding: A significant number of users work at major tech companies and contribute actively to open-source projects.
- Recommendation: Developers should focus on creating or contributing to repositories that emphasize collaborative features, as these are popular in Austin.

Description

This repository contains two primary files, `users.csv` and `repositories.csv`:

- users.csv: Information about each GitHub user in Austin with more than 100 followers.
- repositories.csv: Up to 500 most recent repositories for each user in `users.csv`.

The data was collected using the GitHub API with specific filters to extract users in the Austin area with over 100 followers, including additional attributes for both users and their repositories.

Files

1. users.csv: Contains details about each user, including login, name, company, location, email, bio, and more.
2. repositories.csv: Lists up to 500 repositories per user, including repository name, created date, stars, language, and license type.

Requirements

To run the data collection script, ensure you have:
- A GitHub personal access token for API requests.
- Python 3 and the `requests` library.

Usage

1. Set up your GitHub token in the script.
2. Run the script to collect data.
3. CSV files `users.csv` and `repositories.csv` will be generated in the main directory.
