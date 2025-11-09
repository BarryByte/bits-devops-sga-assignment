# DevOps Assignment Starter

This folder contains a minimal static website for the **Git** portion and a small **Flask** app with a `Dockerfile` for the **Docker** portion.

> Date generated: 2025-11-09

---

## Part 1 — Git & GitHub

### 1. Create local repo
```bash
cd webapp
cd .. # ensure you are in the project root `devops-assignment-starter`
git init
git status
```

### 2. Stage and commit
```bash
git add webapp/*.html .gitignore
git commit -m "feat: add 3-page static website"
git log --oneline --graph
```

### 3. Create and switch branches
```bash
git branch feature/copy-update
git switch feature/copy-update
# make a small edit in webapp/about.html, then:
git add webapp/about.html
git commit -m "chore: update About page copy"
git log --oneline --graph
git switch main  # if main doesn't exist yet, run: git branch -M main
```

### 4. Create GitHub repo and push
```bash
# Create a new empty repo on GitHub (no README), then run:
git branch -M main
git remote add origin https://github.com/<YOUR_USERNAME>/<YOUR_REPO>.git
git push -u origin main
```

Take screenshots of each step above (init, status, add, commit, log, branch, switch, push).

---

## Part 2 — Docker & Docker Hub

### 1. Build the image
```bash
cd docker_app
docker build -t <your-dockerhub-username>/hello-docker:1.0 .
docker images | head
```

### 2. Run the container locally
```bash
docker run --rm -p 8080:8080 <your-dockerhub-username>/hello-docker:1.0
# Visit http://localhost:8080
```

### 3. Push to Docker Hub
```bash
docker login
docker push <your-dockerhub-username>/hello-docker:1.0
```

### 4. Pull & run (optional verification on another machine)
```bash
docker pull <your-dockerhub-username>/hello-docker:1.0
docker run --rm -p 8080:8080 <your-dockerhub-username>/hello-docker:1.0
```

---

## Submission Tips

- Put **all screenshots** and **short captions** into a single Word or PDF file.
- Include:
  - The three HTML files from `webapp/`
  - The Dockerfile and `app.py` + `requirements.txt` from `docker_app/`
- Zip everything for submission.

Good luck!
