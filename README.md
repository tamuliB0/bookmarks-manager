# Bookmarks Manager

### A simple, lightweight web application built with core PHP and MySQL to easily store, organize, and search website links.

It helps users keep track of their favorite web resources from a centralized local dashboard. It features secure database CRUD operations, a simple user interface, and is ready to use with a local DDEV development setup.

---

## 🚀 Features

- **Save & Organize:** Add website links with custom titles, URLs, and descriptive notes.
- **Dynamic Search:** Quickly filter through saved bookmarks to find links instantly.
- **CRUD Functionality:** Create, read, update, and delete bookmarks directly from the interface.
- **Secure Backend:** Implements safe database querying practices to protect data locally.

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
Open your terminal and clone this repository down to your local development workspace:
```bash
git clone [https://github.com/your-username/bookmarks-manager.git](https://github.com/your-username/bookmarks-manager.git)
cd bookmarks-manager
```

### 2. Initialize the DDEV Environment
Set up the container configuration directly within the repository root directory:
```bash
ddev config --project-type=php --docroot=public
```

### 3. Start the Environment
Boot up the local webserver and database containers:
```bash
ddev start
```

### 4. Import the Database Schema
Populate your local MySQL instance using the pre-configured database schema file:
```bash
ddev import-db --file=schema.sql
```
