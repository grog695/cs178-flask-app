# [Your Project Name Here]

**CS178: Cloud and Database Systems — Project #1**
**Author:** [Your Name]
**GitHub:** [your-username]

---

## Overview

<!-- Describe your project in 2-4 sentences. What does it do? Who is it for? What problem does it solve? -->
<!-- This is an in-depth movie database that gives the user the opportunity to create new movies as well as toggling with the other movies in the database. This is useful for any movie enjoyer who wants to access key information about these films. -->
---

## Technologies Used

- **Flask** — Python web framework
- **AWS EC2** — hosts the running Flask application
- **AWS RDS (MySQL)** — relational database for [describe what you stored]
- **AWS DynamoDB** — non-relational database for [describe what you stored]
- **GitHub Actions** — auto-deploys code from GitHub to EC2 on push

---

## Project Structure

```
ProjectOne/
├── flaskapp.py          # Main Flask application — routes and app logic
├── dbCode.py            # Database helper functions (MySQL connection + queries)
├── creds_sample.py      # Sample credentials file (see Credential Setup below)
├── templates/
│   ├── home.html        # Landing page
│   ├── add_user.html     # Adds a new movie to the database
│   ├── delete_user.html     # Deletes a movie from the database
│   ├── update_user.html     # Changes a feature about the movie
│   ├── display_users.html     # Displays the title and release date for every movie in the dataset, but can display any list the user may like through SQL
├── .gitignore           # Excludes creds.py and other sensitive files
└── README.md
```

---

## How to Run Locally

1. Clone the repository:

   ```bash
   git clone https://github.com/grog695/cs178-flask-app.git
   cd your-repo-name
   ```

2. Install dependencies:

   ```bash
   pip3 install flask pymysql boto3
   ```

3. Set up your credentials (see Credential Setup below)

4. Run the app:

   ```bash
   python3 flaskapp.py
   ```

5. Open your browser and go to `http://127.0.0.1:8080`

---

## How to Access in the Cloud

The app is deployed on an AWS EC2 instance. To view the live version:

```
http://18.215.153.145:8080
```

_(Note: the EC2 instance may not be running after project submission.)_

---

## Credential Setup

This project requires a `creds.py` file that is **not included in this repository** for security reasons.

Create a file called `creds.py` in the project root with the following format (see `creds_sample.py` for reference):

```python
# creds.py — do not commit this file
host = "database-2.cilkwumgg1g9.us-east-1.rds.amazonaws.com"
user = "admin"
password = "ungrogged9339"
db = "movies"
```

---

## Database Design

### SQL (MySQL on RDS)

<!-- Briefly describe your relational database schema. What tables do you have? What are the key relationships? -->
<!-- The movie database has a very complex schema, with it consisting of seventeen tables. The most significant relationships that are likely to be used by users are with movie and movie cast, and with movie and genre. -->

**Example:**

- `[movie]` — stores [title,budget,release_date,etc.]; primary key is `[title]`

The JOIN query used in this project: <!-- describe it in plain English -->

### DynamoDB

<!-- Describe your DynamoDB table. What is the partition key? What attributes does each item have? How does it connect to the rest of the app? -->

- **Table name:** `[your-table-name]`
- **Partition key:** `[key-name]`
- **Used for:** [description]

---

## CRUD Operations

| Operation | Route      | Description    |
| --------- | ---------- | -------------- |
| Create    | `/add_user` | [Adds a movie, with it requiring at least a title and release date] |
| Read      | `/display_users` | [Displays all movies from the query] |
| Update    | `/update_user` | [Updates variables from an existing movie. This variable will be input by the user] |
| Delete    | `/delete_user` | [Deletes a movie from the database by title alone] |

---

## Challenges and Insights

<!-- What was the hardest part? What did you learn? Any interesting design decisions? -->
<!-- Personally, I believe the hardest part of this project was incorporating the DynamoDB database. I do not feel confident in how I did on that. -->

---

## AI Assistance

<!-- List any AI tools you used (e.g., ChatGPT) and briefly describe what you used them for. Per course policy, AI use is allowed but must be cited in code comments and noted here. -->
<!-- Google Gemini assistance was used on the update_user.html file. -->