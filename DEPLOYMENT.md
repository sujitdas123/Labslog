# Deployment Guide

This guide covers deploying the Lab Management System to various hosting platforms.

## Quick Deploy Options

### 🚀 Vercel (Recommended)

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/yourusername/lab-management-system)

1. **Connect Repository**
   - Sign up for Vercel
   - Connect your GitHub account
   - Import your repository

2. **Environment Variables**
   Add these in Vercel dashboard:
   ```
   DATABASE_URL=postgresql://username:password@host:5432/database
   VITE_FIREBASE_API_KEY=your_firebase_api_key
   VITE_FIREBASE_PROJECT_ID=your_firebase_project_id
   VITE_FIREBASE_APP_ID=your_firebase_app_id
   ```

3. **Deploy**
   - Vercel will auto-deploy on git push
   - Custom domains supported

### 🌐 Netlify

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/yourusername/lab-management-system)

1. **Connect Repository**
   - Sign up for Netlify
   - Connect GitHub repository
   - Configure build settings

2. **Build Settings**
   ```
   Build command: npm run build
   Publish directory: dist
   ```

3. **Environment Variables**
   Add in Netlify dashboard:
   ```
   DATABASE_URL=your_database_url
   VITE_FIREBASE_API_KEY=your_firebase_api_key
   VITE_FIREBASE_PROJECT_ID=your_firebase_project_id
   VITE_FIREBASE_APP_ID=your_firebase_app_id
   ```

### 🚂 Railway

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/new/template/your-template-id)

1. **Connect Repository**
   - Sign up for Railway
   - Connect GitHub repository
   - Railway auto-detects configuration

2. **Environment Variables**
   Add in Railway dashboard:
   ```
   DATABASE_URL=postgresql://username:password@host:5432/database
   VITE_FIREBASE_API_KEY=your_firebase_api_key
   VITE_FIREBASE_PROJECT_ID=your_firebase_project_id
   VITE_FIREBASE_APP_ID=your_firebase_app_id
   ```

3. **Database**
   - Railway provides PostgreSQL addon
   - Automatically sets DATABASE_URL

### 🎨 Render

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/yourusername/lab-management-system)

1. **Connect Repository**
   - Sign up for Render
   - Connect GitHub repository
   - Choose "Web Service"

2. **Build Configuration**
   ```
   Build Command: npm run build
   Start Command: npm start
   ```

3. **Environment Variables**
   Add in Render dashboard:
   ```
   DATABASE_URL=postgresql://username:password@host:5432/database
   VITE_FIREBASE_API_KEY=your_firebase_api_key
   VITE_FIREBASE_PROJECT_ID=your_firebase_project_id
   VITE_FIREBASE_APP_ID=your_firebase_app_id
   ```

## Manual Deployment

### Prerequisites

- Node.js 18+
- PostgreSQL database
- Firebase project

### Build Process

1. **Clone Repository**
   ```bash
   git clone https://github.com/yourusername/lab-management-system.git
   cd lab-management-system
   ```

2. **Install Dependencies**
   ```bash
   npm install
   ```

3. **Set Environment Variables**
   ```bash
   cp .env.example .env
   # Edit .env with your values
   ```

4. **Build Application**
   ```bash
   npm run build
   ```

5. **Start Production Server**
   ```bash
   npm start
   ```

### Environment Variables

Required environment variables:

| Variable | Description | Required |
|----------|-------------|----------|
| `DATABASE_URL` | PostgreSQL connection string | Yes |
| `VITE_FIREBASE_API_KEY` | Firebase API key | Yes |
| `VITE_FIREBASE_PROJECT_ID` | Firebase project ID | Yes |
| `VITE_FIREBASE_APP_ID` | Firebase app ID | Yes |
| `NODE_ENV` | Environment (production/development) | No |
| `PORT` | Server port (default: 5000) | No |

### Database Setup

1. **Create Database**
   ```sql
   CREATE DATABASE labmanagement;
   ```

2. **Run Migrations**
   ```bash
   npm run db:push
   ```

3. **Verify Connection**
   ```bash
   npm run db:check
   ```

## Platform-Specific Guides

### Vercel

```javascript
// vercel.json
{
  "version": 2,
  "builds": [
    {
      "src": "dist/index.js",
      "use": "@vercel/node"
    },
    {
      "src": "dist/public/**",
      "use": "@vercel/static"
    }
  ],
  "routes": [
    {
      "src": "/api/(.*)",
      "dest": "dist/index.js"
    },
    {
      "src": "/(.*)",
      "dest": "dist/public/$1"
    }
  ]
}
```

### Netlify

```toml
# netlify.toml
[build]
  command = "npm run build"
  publish = "dist"

[[redirects]]
  from = "/api/*"
  to = "/.netlify/functions/api/:splat"
  status = 200

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```

### Railway

```json
// railway.json
{
  "deploy": {
    "startCommand": "npm start",
    "healthcheckPath": "/api/health"
  }
}
```

### Render

```yaml
# render.yaml
services:
  - type: web
    name: lab-management-system
    env: node
    buildCommand: npm run build
    startCommand: npm start
    envVars:
      - key: DATABASE_URL
        sync: false
      - key: VITE_FIREBASE_API_KEY
        sync: false
      - key: VITE_FIREBASE_PROJECT_ID
        sync: false
      - key: VITE_FIREBASE_APP_ID
        sync: false
```

## Database Providers

### Free PostgreSQL Options

1. **Neon** (Recommended)
   - 3GB free tier
   - Excellent performance
   - Easy setup

2. **Supabase**
   - 500MB free tier
   - Additional features
   - Good documentation

3. **PlanetScale**
   - MySQL alternative
   - Generous free tier
   - Branching feature

4. **Railway PostgreSQL**
   - Integrated with Railway
   - $5/month after trial
   - Easy setup

### Connection String Format

```
postgresql://username:password@host:port/database
```

Example:
```
postgresql://user:pass@host.com:5432/labmanagement
```

## Security Considerations

### Environment Variables

- Never commit secrets to git
- Use platform-specific secret management
- Rotate keys regularly
- Use minimal permissions

### Database Security

- Use connection pooling
- Enable SSL connections
- Regular backups
- Monitor access logs

### Application Security

- Keep dependencies updated
- Use HTTPS in production
- Implement rate limiting
- Regular security audits

## Performance Optimization

### Build Optimization

```javascript
// vite.config.ts
export default defineConfig({
  build: {
    rollupOptions: {
      output: {
        manualChunks: {
          vendor: ['react', 'react-dom'],
          ui: ['@radix-ui/react-dialog', '@radix-ui/react-dropdown-menu']
        }
      }
    }
  }
});
```

### Caching Strategy

- Static assets: Long-term caching
- API responses: Short-term caching
- Database queries: Connection pooling
- CDN: Geographic distribution

## Monitoring and Logging

### Health Checks

```javascript
// Health check endpoint
app.get('/api/health', (req, res) => {
  res.json({ status: 'ok', timestamp: new Date() });
});
```

### Error Tracking

- Implement error boundaries
- Log errors to external service
- Monitor performance metrics
- Set up alerts

## Backup Strategy

### Database Backups

- Daily automated backups
- Point-in-time recovery
- Cross-region replication
- Regular restore testing

### Application Backups

- Git repository backups
- Environment configuration
- Static assets backup
- Documentation backup

## Scaling Considerations

### Horizontal Scaling

- Load balancer configuration
- Database read replicas
- CDN implementation
- Microservices architecture

### Vertical Scaling

- Resource monitoring
- Performance profiling
- Memory optimization
- CPU optimization

## Troubleshooting

### Common Issues

1. **Build Failures**
   - Check Node.js version
   - Verify dependencies
   - Review build logs

2. **Database Connection**
   - Verify connection string
   - Check network access
   - Review SSL settings

3. **Environment Variables**
   - Verify variable names
   - Check platform settings
   - Review application logs

### Debug Mode

```bash
# Enable debug logging
DEBUG=* npm start

# Check application logs
npm run logs
```

## Support

- **Documentation**: Check project README
- **Issues**: Report on GitHub
- **Community**: Join discussions
- **Professional**: Contact maintainers

---

**Happy Deploying! 🚀**