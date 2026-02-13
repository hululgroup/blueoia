# 🎯 Hulul Task Manager

A real-time task management dashboard for tracking Hulul Group projects and sub-agent tasks.

## Features

- ✅ Live task tracking with auto-refresh (30s)
- ✅ Sub-agent progress monitoring
- ✅ Visual stats and status indicators
- ✅ Neobrutalist design aesthetic
- ✅ Mobile responsive

## Tech Stack

- Static HTML/CSS/JS
- Space Grotesk font
- Font Awesome icons
- Nginx (production)

## Local Development

```bash
# Serve with any static server
python3 -m http.server 8080

# Or use Docker
docker-compose up
```

## Deploy to Dokploy

### Option 1: Using Git Repository

1. Push this folder to GitHub
2. In Dokploy, create new project → "Git Repository"
3. Connect your GitHub account
4. Select this repository
5. Build type: Dockerfile
6. Deploy!

### Option 2: Using Docker Image

1. Build and push to Docker Hub:
```bash
docker build -t yourusername/hulul-task-manager .
docker push yourusername/hulul-task-manager
```

2. In Dokploy, create new project → "Docker Image"
3. Enter image name: `yourusername/hulul-task-manager`
4. Deploy!

### Option 3: Using Docker Compose

1. Push to GitHub
2. In Dokploy, create new project → "Docker Compose"
3. Select repository
4. Dokploy will use `docker-compose.yml`
5. Deploy!

## Environment Variables

None required - this is a static frontend app.

## Ports

- Container exposes port `80`
- Dokploy will map this to your domain

## Updating Tasks

To update tasks, edit the `index.html` file directly or integrate with an API backend.

---

Built for Hulul Group
