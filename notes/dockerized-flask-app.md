Absolutely, Tushar! 💯 Let’s do a **complete breakdown of what you did on Day 6**, including the **purpose of each file**, **every line of code**, and **how it all worked together** in Docker.

---

## 🐳 **DAY 6: Dockerize Flask App (Line-by-Line Breakdown)**

---

### 📁 Folder Structure

```
docker/flask-app/
├── app.py
├── requirements.txt
└── Dockerfile
```

---

## 1️⃣ `app.py` – Your Flask App

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello():
    return "Hello from Dockerized Flask App!"

if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0')
```

### 🔍 Line-by-Line Explanation:

* `from flask import Flask`
  → Imports the **Flask web framework**.

* `app = Flask(__name__)`
  → Creates a Flask app object. `__name__` helps Flask locate files.

* `@app.route('/')`
  → Sets a **route** for the homepage (URL: `/`).

* `def hello(): return ...`
  → The function returns a string when someone visits the site.

* `if __name__ == '__main__':`
  → Only runs the app when this script is executed directly.

* `app.run(debug=True, host='0.0.0.0')`
  → `debug=True`: auto-reloads on change
  → `host='0.0.0.0'`: makes the app accessible **outside the container**

---

## 2️⃣ `requirements.txt` – Python Dependencies

```txt
flask
```

### 🔍 Explanation:

* Lists the packages needed.
* Docker will use this to run:

  ```bash
  pip install -r requirements.txt
  ```
* Here, only **Flask** is required.

---

## 3️⃣ `Dockerfile` – Instructions to Build the Image

```Dockerfile
# Use official Python image
FROM python:3.11-slim

# Set working directory inside container
WORKDIR /app

# Copy all files from local folder to container
COPY . .

# Install all dependencies
RUN pip install -r requirements.txt

# Expose the port Flask will run on
EXPOSE 5000

# Run the app
CMD ["python", "app.py"]
```

### 🔍 Line-by-Line Explanation:

* `FROM python:3.11-slim`
  → Start from a **lightweight Python 3.11** image from DockerHub

* `WORKDIR /app`
  → Creates a folder `/app` inside the container and works inside it

* `COPY . .`
  → Copies all local files into `/app` inside the container

* `RUN pip install -r requirements.txt`
  → Installs Flask inside the container

* `EXPOSE 5000`
  → Tells Docker that this container will **use port 5000**

* `CMD ["python", "app.py"]`
  → This is the **default command** when the container runs
  It starts the Flask app

---

## 🔨 4️⃣ Build Docker Image

```bash
docker build -t flask-docker-app .
```

### 🔍 What this does:

* Reads the `Dockerfile`
* Creates a new image called `flask-docker-app`
* Installs everything and saves it as a portable container image

---

## 🚀 5️⃣ Run Docker Container
```bash
### 🔍 What this does:

* Runs the container using the image
* `-p 5000:5000` maps:

  * **port 5000 on your computer → port 5000 inside container**
* Now you can access Flask at:
  👉 [http://localhost:5000](http://localhost:5000)

---

## ✅ Summary of What You Achieved Today

| 📦 Wrote Dockerfile     | Instructions to build app in a container     |
| 🔧 Built Docker image   | Container image with Flask app inside        |
| 🏃‍♂️ Ran the container | Accessed your Flask app in the browser       |
| 📑 Documented progress  | `day6-docker-flask.md` + committed to GitHub |

---


