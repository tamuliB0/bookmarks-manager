# Bookmarks Manager

### A simple, lightweight web application built with core PHP and MySQL to easily store, organize, and search website links.

Bookmarks Manager is a local PHP/MySQL dashboard for saving, tagging, and searching website links. It covers the full lifecycle of a bookmark: saving it with tags, bulk-importing a list of URLs, searching and filtering by tag, sorting and paginating results, starring favorites, and bulk-editing or deleting selected bookmarks.

---

## 🚀 Features

- **Save & Organize:** Add a bookmark with a title, URL, and notes; tag it by checking existing tags or typing a new one, resolved through `findOrCreateTag()`. Bookmarks and tags are linked via a `bookmark_tags` junction table.
- **Bulk Import:** Paste a list of URLs (newline- or comma-separated) — each is fetched with a spoofed User-Agent, parsed with `DOMDocument` to scrape the page's `<title>`, and inserted only if the URL isn't already saved.
- **Dynamic Search & Filter:** Filter by tag or search titles with a `LIKE` query, with `%` and `_` escaped so the search stays literal.
- **Sorting & Pagination:** Sort by title or date, ascending or descending, through an allow-list mapping that blocks arbitrary column injection; results are paginated with `LIMIT`/`OFFSET` bound as `PDO::PARAM_INT`.
- **Favorites:** Star a bookmark to pin it above the rest (`favourite DESC` in the sort order).
- **Bulk Actions:** Select multiple bookmarks via checkboxes to bulk-delete or bulk-tag them in a single request.
- **Full CRUD:** Create, read, update, and delete bookmarks end-to-end, with every ID from a form or URL validated via `ctype_digit()` before it reaches a query.
- **Secure Backend:** All database access goes through PDO prepared statements, URLs validated with `filter_var(..., FILTER_VALIDATE_URL)`, and tag relationships cleaned up automatically via `ON DELETE CASCADE`.

---

## 🛠️ Built With

- **Language:** PHP 8.3.6
- **Database:** MySQL 8.0.46
- **Local Environment:** DDEV 1.25.2

---

## 📋 Prerequisites

Before setting up the project, ensure you have DDEV installed on your machine. DDEV manages your PHP version, web server, and database automatically.
- [DDEV CLI](https://ddev.readthedocs.io/)

---

## ⚙️ Getting Started

Follow these simple steps to initialize and run the application in your local environment using DDEV:

### 1. Clone the Repository
```bash
git clone https://github.com/tamuliB0/bookmarks-manager.git
cd bookmarks-manager
```

### 2. Initialize the DDEV Environment
```bash
ddev config --project-type=php --docroot=public
```

### 3. Start the Environment
```bash
ddev start
```

### 4. Import the Database Schema
Populate your local MySQL instance with the `bookmarks`, `tags`, and `bookmark_tags` tables, plus a few sample rows to verify the setup:
```bash
ddev import-db --file=schema.sql
```

## 💻 Usage

### 🌐 Live Demo
You can try out the live production build of the application here:
👉 **[Live Demo Dashboard](http://www.bhardwaj.lovestoblog.com/bookmarks/)**

---

### 🏠 Local Development
Once your DDEV containers are fully up and running locally, you can access your local development instance in your browser:

* **Local URL:** `https://bookmarks-manager.ddev.site`
