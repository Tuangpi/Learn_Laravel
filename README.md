# Learn Laravel

Simple Laravel 9 blog-style app for managing articles and comments.

## Features

- View a paginated list of articles
- Open an article detail page
- Create new articles after logging in
- Add comments to articles after logging in
- Delete your own comments
- Delete articles from the detail page

## Tech Stack

- PHP 8
- Laravel 9
- Laravel UI authentication
- Bootstrap 5
- MySQL or another Laravel-supported database

## Project Structure

- `app/Http/Controllers/Article` handles article and comment actions
- `app/Models` contains `Article`, `Category`, and `Comment`
- `resources/views/articles` contains the article pages
- `routes/web.php` defines the web routes

## Main Routes

- `GET /` - article list
- `GET /articles` - article list
- `GET /articles/detail/{id}` - article detail
- `GET /articles/add` - article create form
- `POST /articles/add` - save article
- `POST /comments/add` - save comment

## Setup

1. Install PHP dependencies:

```bash
composer install
```

2. Install frontend dependencies:

```bash
npm install
```

3. Create the environment file:

```bash
cp .env.example .env
```

4. Generate the application key:

```bash
php artisan key:generate
```

5. Configure your database in `.env`.

6. Run migrations and seed sample data:

```bash
php artisan migrate --seed
```

7. Build frontend assets:

```bash
npm run dev
```

8. Start the local server:

```bash
php artisan serve
```

Then open `http://127.0.0.1:8000`.

## Demo Users

The seeder creates two sample users:

- `alice@gmail.com`
- `bob@gmail.com`

If you want to log in with them, set a password manually in the database or update the seeder to include one before running `php artisan db:seed`.

## Notes

- Article list pages show 5 items per page.
- Guests can browse articles, but login is required to create articles or comments.
- Comment deletion is restricted to the user who created the comment.
