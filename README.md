# DevOps TV Show API: Complete CI/CD Pipeline


## How to Test the Live API (Start Here!)

*Note for the reviewer: The original lab instructions mentioned testing a generic `/api/hello` or `/actuator/health` endpoint. I built a custom TV Show database instead, so the correct endpoint to test the live database connection is `/tvshows`.*

My live Render URL is: `https://may-7-github-actions.onrender.com`

You can test the API using any of these three methods:

**1. The Quick Browser Test (Easiest)**
Just click this link: [https://may-7-github-actions.onrender.com/tvshows](https://may-7-github-actions.onrender.com/tvshows)


**2. The Terminal Test (cURL)**
Open your terminal and run:
`curl https://may-7-github-actions.onrender.com/tvshows`

**3. The Postman Test**
Send a standard `GET` request to `https://may-7-github-actions.onrender.com/tvshows`. You should receive a `200 OK` status and the formatted JSON data.

---

##  The Automation  Flow

If you want to see the automationin action, check out the **Actions** tab in this repository.
1. I push code.

2. `Actions App CI` runs and tests the build.
3. If it passes, `Deploy to Render` triggers automatically and updates the live API.

No manual clicking required !