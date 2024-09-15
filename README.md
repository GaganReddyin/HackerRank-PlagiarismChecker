# HackerRank-PlagiarismChecker
# HackerRank Plagiarism Checker

## Overview

This project scrapes data from the HackerRank dashboard to track student attempts and stores the results in a MySQL database. It uses Python with Selenium for web scraping and SQL for data storage.

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

## Code Explanation

### `main.py`

This FastAPI backend file defines endpoints to interact with the application.

```python
from fastapi import FastAPI, Depends
from sqlalchemy.orm import Session
import models
import crud

app = FastAPI()

class StudentData(BaseModel):
    username: str
    contest_name: str

@app.post("/fetch_attempts/")
def fetch_attempts(data: StudentData, db: Session = Depends(get_db)):
    result = crud.fetch_student_attempts(db, data.username, data.contest_name)
    return result

def get_db():
    db = models.SessionLocal()
    try:
        yield db
    finally:
        db.close()
