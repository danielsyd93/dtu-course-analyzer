# DTU Course Analyzer

## Installation
https://chrome.google.com/webstore/detail/dtu-course-analyzer/bimhgdngikcnelkhjindmdghndfmdcde

## Chrome extension
The following is an explanation of how the values were calculated (higher is better)
  * Average grade
  * Average grade percentile: All courses are ranked against eachother based on average grade. 
  * Percent passed: The ratio of people who **attended** the exam that passed.
  * Course rating percentile: All course are ranked based on the question "Overall I think the course is good" from course reviews. 
  * Workscore percentile: Ranked based on the question "5 points are allocated to 9h./week (45 h./week in the 3-week period). I think my workload in the course is [Much less..Much more]"
  * Lazyscore: The average percentile between percent passed and workload. This is a metric for how much beer one can drink during a semester and still get decent grades. 🍺🍺🍺

## Data gathering and analysis
Data was gathered using a Python script that scraped DTU's coursebase and formatted it so that the extension can use it.

# Development
## Setup
 1. Install python dependencies `pip3 install -r requirements.txt`

## Gather data
 1. Update the list of courses using getCourseNumbers.js
 2. Create a file called `secret.txt` containing the `ASP.NET_SessionId` cookie set when entering https://kurser.dtu.dk. Make sure there is no leading or trailing whitespace and newlines
 3. Run the scraper `python3 scraper.py`
 4. Analyze the data for Chrome using `python3 analyzer.py chrome_extension`
 5. Analyze the data for Firefox using `python3 analyzer.py firefox_extension`
