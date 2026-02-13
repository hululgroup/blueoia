# Deployment Guide for Dokploy

## Quick Steps

### 1. Push to GitHub (if not already)

```bash
cd /home/admin/.openclaw/workspace/hulul-task-manager
git init
git add .
git commit -m "Initial commit: Task Manager"
git remote add origin https://github.com/hululgroup/hulul-task-manager.git
git push -u origin main
```

### 2. In Dokploy Dashboard

1. Go to your Dokploy instance
2. Click **"Create Project"**
3. Select **"Git Repository"**
4. Choose **GitHub** and connect your account
5. Select repository: `hululgroup/hulul-task-manager`
6. Build Type: **Dockerfile**
7. Click **"Deploy"**

### 3. Configure Domain

1. In the project settings, go to **Domains**
2. Add your domain: `tasks.hulul.group` (or subdomain)
3. Dokploy will automatically handle SSL

### 4. Done! 🎉

Your task manager will be live at: `https://tasks.hulul.group`

---

## Alternative: Deploy via Docker Image

If you prefer not to use Git:

```bash
# Build locally
docker build -t hululgroup/task-manager:latest .

# Push to Docker Hub
docker login
docker push hululgroup/task-manager:latest

# In Dokploy, select "Docker Image" and use:
# hululgroup/task-manager:latest
```

---

## Auto-Deploy on Git Push

Dokploy supports webhooks for auto-deployment:

1. In Dokploy → Project Settings → Webhooks
2. Copy the webhook URL
3. In GitHub → Repository Settings → Webhooks
4. Add the Dokploy webhook URL
5. Select "Push" events

Now every push to GitHub will auto-deploy! 🚀

---

## Troubleshooting

**Build fails?**
- Check Dockerfile syntax
- Ensure all files are committed

**Port issues?**
- Container exposes port 80
- Dokploy maps this automatically

**Domain not working?**
- Check DNS points to Dokploy server
- Verify SSL certificate generated
