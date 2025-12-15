# 🐍 python-github-api

A beginner-friendly Python project that uses the **GitHub REST API** to fetch and display public information about a GitHub user.

---

## 📌 Project Overview
This project takes a GitHub username as input and retrieves user details such as name, number of public repositories, and followers using Python and the `requests` library.  
It also demonstrates **API handling**, **JSON parsing**, and **exception handling**.

---

## 📂 Project Structure
python-github-api/
│
├── github_api.py
└── README.md


---


---

## 🧑‍💻 Code
```python
import requests

try:
    # Step 1: Take username input
    username = input("Enter GitHub username: ")

    # Step 2: GitHub API URL
    url = f"https://api.github.com/users/{username}"

    # Step 3: Call API
    response = requests.get(url)

    # Step 4: Check if user exists
    if response.status_code != 200:
        raise Exception("GitHub user not found")

    # Step 5: Convert JSON to Python dictionary
    data = response.json()

    # Step 6: Print required information
    print("\nGitHub User Details:")
    print("Name:", data.get("name"))
    print("Public Repositories:", data.get("public_repos"))
    print("Followers:", data.get("followers"))

except Exception as e:
    print("Error:", e)

finally:
    print("Program finished")

