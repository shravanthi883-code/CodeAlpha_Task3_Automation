# Task 3: Scrape the title of a fixed webpage and save it

import requests
import re

# Step 1: Define the URL
url = "https://www.example.com"  # You can replace this with any static webpage

# Step 2: Send a GET request
response = requests.get(url)

# Step 3: Extract the title using regex
match = re.search(r"<title>(.*?)</title>", response.text, re.IGNORECASE)
if match:
    title = match.group(1)
    print(f"📄 Page Title: {title}")

    # Step 4: Save to a file
    with open("page_title.txt", "w", encoding="utf-8") as file:
        file.write(f"Title of {url}:\n{title}")
    print("✅ Title saved to 'page_title.txt'")
else:
    print("❌ Title not found.")# CodeAlpha_Task3_Automation
