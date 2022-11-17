# syt5-gk961-cloud-datenmanagement-rest_damianik_5bhit created by GitHub Classroom

## Entwicklung
Dies ist die Abgabe von Philip Damianik für das Modul GK961 Middleware Engineering "Cloud Data-Interface" (BORM).

Das verwendete Framework ist [Laravel 9](https://laravel.com/).

Um ein einfaches Setup zu ermöglichen, wurde das Framework mit [Laravel Sail](https://laravel.com/docs/9.x/sail) in einer Docker-Container Umgebung installiert.
Die Datenbank ist MySQL und wurde mit Laravel Sail als Service installiert.

Für die grundsätzliche Benutzerverwaltung wurde das [Laravel Breeze "API"](https://laravel.com/docs/9.x/starter-kits#breeze-and-next) Starter Kit verwendet.
Da dieses davon ausgeht, dass man auf der Client Seite nicht nur Cookies sondern auch Headers speichert und verwaltet wurde CSRF Protection deaktiviert.
Ansonsten hat dieses Breeze Starter Kit bereits die notwendigen Routen und Nutzermodelle für die Authentifizierung mitgebracht.

## Setup

### Voraussetzungen

 - Docker & Docker Compose
 - php >= 8.0.2
 - composer

### Installation

```shell
cp .env.example .env
php artisan key:generate
composer install
```

### Starten der Container

```shell
./vendor/bin/sail up -d
```

## Testen

### Register

```shell
curl -X POST -H 'Accept:application/json' 'localhost/register' \
-F 'name="Max Mustermann"' \
-F 'email="max.mustermann@example.org"' \
-F 'password="password1"'
```

### Login

```shell
curl -X POST -H 'Accept:application/json' 'localhost/login' \
-F 'email="max.mustermann@example.org"' \
-F 'password="password1"'
```

