# HackerRank-PlagiarismChecker

## Overview

This project scrapes data from the HackerRank dashboard to track student attempts and stores the results in a MySQL database. It uses Python with Selenium for web scraping and SQL for data storage.

## Tech Stack

- **Backend Framework**: [FastAPI](https://fastapi.tiangolo.com/)
- **Web Scraping**: [Selenium](https://www.selenium.dev/)
- **Database**: [MySQL](https://www.mysql.com/)
- **ORM**: [SQLAlchemy](https://www.sqlalchemy.org/)
- **Python Libraries**: 
  - `uvicorn` for ASGI server
  - `pymysql` for MySQL connection
    
## Prerequisites

1. **Install Dependencies**: Ensure you have Python and `pip` installed. Then install the required Python packages.

    ```bash
    pip install fastapi uvicorn selenium sqlalchemy pymysql
    ```

2. **Setup MySQL**: Install and configure MySQL on your local machine.

## Configuration

### HackerRank Inputs

- **Admin Username**: Your HackerRank admin username.
- **Admin Password**: Your HackerRank admin password.
- **Student Username**: The username of the student whose data you want to fetch.
- **Contest Name**: The name of the contest to scrape.

### MySQL Configuration

- **Username**: Your MySQL username.
- **Password**: Your MySQL password.
- **Database**: The name of your MySQL database.
- **Host**: The host where MySQL is running (default is localhost).




