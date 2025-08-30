# Laravel Dev Container for GitHub Codespaces

A complete Laravel development environment ready for GitHub Codespaces with PHP 8.4, Node.js 22, MySQL, and essential development tools.

## Features

- **PHP 8.4** with essential extensions (GD, MySQL, SQLite, Redis, Xdebug)
- **Node.js 22** with npm for frontend development
- **MySQL 8.0** database with health checks
- **Xdebug** configured for debugging
- **Laravel Installer** pre-installed
- **VS Code extensions** for Laravel development
- **Port forwarding** for Laravel app (8000) and Vite dev server (5173)

## Quick Start

### Option 1: Use as Template
1. Click "Use this template" to create a new repository
2. Open in GitHub Codespaces
3. Create a new Laravel project:
   ```bash
   laravel new my-app
   cd my-app
   ```

### Option 2: Clone Existing Laravel Project
1. Clone your Laravel project into this dev container
2. The container will automatically run `composer install` and `npm install`
3. Configure your `.env` file with the database settings below

## Database Configuration

The dev container includes a MySQL 8.0 database. Add these settings to your Laravel `.env` file:

```env
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=laravel
DB_USERNAME=laravel
DB_PASSWORD=password
```

## Included VS Code Extensions

- **Laravel Extension Pack** - Laravel syntax and snippets
- **PHP Debug** - Xdebug integration
- **PHP Tools** - Advanced PHP development features
- **Claude Code** - AI-powered coding assistant

## Port Configuration

| Port | Service | Auto-forward |
|------|---------|--------------|
| 8000 | Laravel Application | ✅ (with notification) |
| 3306 | MySQL Database | ✅ (silent) |
| 5173 | Vite Dev Server | ✅ |

## Development Workflow

1. **Start Laravel development server:**
   ```bash
   php artisan serve --host=0.0.0.0 --port=8000
   ```

2. **Run database migrations:**
   ```bash
   php artisan migrate
   ```

3. **Start Vite for frontend development:**
   ```bash
   npm run dev -- --host=0.0.0.0
   ```

## Debugging

Xdebug is pre-configured and ready to use:
- **Mode:** Debug
- **Port:** 9003
- **Trigger:** On request
- Set breakpoints in VS Code and start debugging your Laravel application

## Database Management

Access MySQL directly:
```bash
mysql -h mysql -u laravel -p
# Password: password
```

Or use Laravel's database tools:
```bash
php artisan tinker
php artisan db:show
```

## Customization

- **Add PHP extensions:** Modify `.devcontainer/Dockerfile`
- **Add VS Code extensions:** Update `.devcontainer/devcontainer.json`
- **Environment variables:** Update `.devcontainer/docker-compose.yml`

## Container Details

- **Base Image:** `cosmospham/laravel-dev-container:latest`
- **PHP Version:** 8.4-cli
- **Node.js Version:** 22
- **MySQL Version:** 8.0
- **User:** `vscode` with sudo privileges

## Troubleshooting

**Container fails to start:**
- Check Docker resources availability
- Verify MySQL container health status

**Database connection issues:**
- Ensure MySQL container is healthy: `docker-compose ps`
- Verify environment variables in `.env`

**Port conflicts:**
- Check if ports 8000, 3306, or 5173 are already in use
- Modify port mappings in `docker-compose.yml` if needed

---

Ready to build amazing Laravel applications in the cloud! 🚀