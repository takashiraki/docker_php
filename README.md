# Docker PHP Development Environment

A Docker containerized PHP development environment with Apache, PHP 8.3, Xdebug, and SSL support.

## Features

- PHP 8.3 + Apache
- Xdebug for debugging
- MySQL extensions (mysqli, pdo_mysql)
- GitHub CLI integration
- SSL/TLS support with Let's Encrypt
- Multi-network configuration

## Quick Start

1. Copy `.env.example` to `.env` and configure variables
2. Run `docker-compose up -d`
3. Place PHP files in `src/` directory

## Structure

```
docker_php/
├── docker-compose.yml
├── php/Dockerfile
├── php/php.ini
└── src/index.php
```
