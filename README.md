# TDS-1
Austin Users and Repositories

Description

This repository contains two primary files, `users.csv` and `repositories.csv`:

- users.csv: Information about each GitHub user in Austin with more than 100 followers.
- repositories.csv: Up to 500 most recent repositories for each user in users.csv. 

The data was collected using the GitHub API with specific filters to extract users in the Austin area with over 100 followers, including additional attributes for both users and their repositories.

Files

1. users.csv: Contains details about each user, including login, name, company, location, email, bio, and more. Saved 471 users to users.csv
2. repositories.csv: Lists up to 500 repositories per user, including repository name, created date, stars, language, and license type. Saved 41660 repositories here.

Requirements

To run the data collection script, ensure you have:
- A GitHub personal access token for API requests.
- Python 3 and the `requests` library.

Usage

1. Set up your GitHub token in the script.
2. Run the script to collect data.
3. CSV files `users.csv` and `repositories.csv` will be generated in the main directory.

DETAILS:

- Data was scraped from the GitHub API based on users in Austin with over 100 followers and includes their public repositories.Details shared below.

The script written for scraping, effectively automates the data scraping process from GitHub's API, targeting specific users based on location and follower count. By structuring the data retrieval into distinct functions, it makes the script modular and easier to maintain. The end result is two well-organized CSV files that provide valuable insights into GitHub users in Austin, their profile details, and their public repositories.

This script was designed to scrape user and repository data from GitHub's API, specifically targeting users located in Austin with more than 100 followers. It gathers user information and their associated public repositories, ultimately saving this data into two CSV files for later analysis.

Starting with importing necessary libraries: requests for making HTTP requests and csv for handling CSV file operations.
A personal access token (GITHUB_TOKEN) was set up for authentication with the GitHub API. This token allows access to the API and must be kept confidential.

MODULES:

1. Cleaning Company Names: 

The clean_company_name function is defined to standardize company names by removing leading whitespace and the '@' character. It also converts names to uppercase to ensure consistency across records.

Fetching User Data: 

The fetch_users function is responsible for retrieving users from GitHub:
It constructs a search URL that queries users based on their location (Austin) and a minimum follower count (100).
The function uses pagination to fetch results in chunks of up to 100 users per request.
For each user found, it sends a GET request to fetch detailed information about the user, including their login name, full name, company, location, email, hireable status, biography, number of public repositories, followers, following count, and creation date.
The function accumulates this information in a list of dictionaries (users) until no more users are available (i.e., the API returns no items).

2. Fetching User Repositories:

The fetch_repositories function collects repository data for each user:
It sends GET requests to the user's repositories endpoint and handles pagination to retrieve all repositories.
For each repository, it gathers key details such as the repository's full name, creation date, star count, watcher count, primary language, project status, wiki status, and license name.
The gathered repository information is stored in a list of dictionaries (repositories) for later use.

3. Saving Data to CSV:

The save_users_to_csv and save_repositories_to_csv functions handle writing the collected user and repository data to CSV files:
Each function opens a specified file in write mode and utilizes csv.DictWriter to create a CSV file with headers and rows corresponding to the collected data.
The user data is saved in users.csv, while the repository data is saved in repositories.csv.
Main Execution Logic:

4. Finally the main function orchestrates the script's execution:

It calls the fetch_users function to retrieve user data and saves it to a CSV file.
It then iterates over each fetched user, calling fetch_repositories to get their repository data and accumulating this information in a combined list.
Finally, it saves the combined repository data to a separate CSV file.

Rate Limiting:

The script includes a time.sleep(1) call after each API request to avoid hitting GitHub's API rate limits. This ensures that the script runs smoothly without overwhelming the server.


- Interesting findings:
  
  -  A significant number of users work at major tech companies like Google, Microdoft and even Github and contribute actively to open-source projects.
  -  The top most user based on the followers count was 'getify'.
  -  The most common and top most preferred programming language by the users based on the number of repositories were JavaScript, Python, TypeScript, Go.
  -  Repositories were created in the timeframe of 2008 till present of which the highest number around 3800 were created in 2016.
    
- Recommendation: Developers should focus on creating or contributing to repositories that emphasize collaborative features, as these are popular in Austin.
