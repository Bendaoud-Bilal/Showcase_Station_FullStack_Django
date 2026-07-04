# Showcase Station — Full-Stack Django Freelancer Platform

## Description

**Showcase Station** is a full-stack Django web application designed as a **freelancer showcase platform**. Based on its structure — a dedicated `accounts` app for user authentication, a `freelancers` app for freelancer profiles, and `media/freelancer_photos` for profile image storage — it allows freelancers to create accounts, build a profile, and showcase their work/photos to potential clients or visitors.

The project follows Django's standard project layout (`django_project/` as the settings root) combined with template-driven frontend rendering (`templates/`, `static/`, `staticfiles/`), and uses JavaScript/CSS for interactive/styled frontend behavior alongside Django's server-rendered pages.

## Features

- 👤 **User accounts** — dedicated `accounts` app handling registration, login, and authentication.
- 🧑‍💼 **Freelancer profiles** — dedicated `freelancers` app for creating and displaying freelancer profile information.
- 🖼️ **Profile photo uploads** — supports freelancer photo uploads, stored under `media/freelancer_photos/` and processed via Pillow.
- 🎨 **Template-driven UI** — server-rendered pages via Django templates (`templates/`), styled with custom CSS and enhanced with JavaScript for interactivity.
- 📦 **Static file handling in production** — uses Whitenoise to serve static assets efficiently without a separate web server/CDN.
- 🗄️ **SQLite database** — ships with `db.sqlite3` for straightforward local development without extra database setup.

> Note: Since the repository has no description and its `freelancers`/`accounts` app internals could not be directly inspected, the feature list above reflects what is confidently inferable from the folder structure and dependencies. See **To-do** below for what should be verified/documented further.

## Tech Stack

- **Backend Framework:** Django 5.0.5
- **Image Processing:** Pillow 10.3.0
- **Static Files:** Whitenoise 6.6.0
- **Supporting Libraries:** asgiref 3.8.1, sqlparse 0.5.0, tzdata 2024.1
- **Database:** SQLite (`db.sqlite3`)
- **Frontend:** JavaScript (46.7%), CSS (43.4%), HTML/Django Templates (6.6%)
- **Language:** Python (3.3%)

## Installation

### Prerequisites

- Python 3.9+ and `pip`
- `git`

### 1. Clone the repository

```bash
git clone https://github.com/Bendaoud-Bilal/Showcase_Station_FullStack_Django.git
cd Showcase_Station_FullStack_Django
```

### 2. Create and activate a virtual environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Apply database migrations

```bash
python manage.py migrate
```

### 5. Create a superuser (optional, for admin access)

```bash
python manage.py createsuperuser
```

### 6. Run the development server

```bash
python manage.py runserver
```

The app should now be available at `http://127.0.0.1:8000/`.

## Usage Examples

**Registering and logging in**

1. Navigate to `http://127.0.0.1:8000/` in your browser.
2. Use the registration page (served by the `accounts` app) to create a new account.
3. Log in with your credentials to access freelancer-related features.

**Creating/viewing a freelancer profile (conceptual)**

1. Once logged in, navigate to the freelancer profile section (served by the `freelancers` app).
2. Fill in profile details and upload a profile photo — this is saved under `media/freelancer_photos/`.
3. Visit the public showcase page to see freelancer listings.

**Accessing the Django admin panel**

```bash
http://127.0.0.1:8000/admin/
```
Log in with the superuser credentials created in step 5 of installation to manage users and freelancer entries directly.

## Contributing

Contributions are welcome:

1. **Fork** the repository.
2. **Create a feature branch:**
```bash
   git checkout -b feature/your-feature-name
```
3. **Make your changes**, following the existing Django app structure (`accounts/`, `freelancers/`).
4. **Run migrations and test locally:**
```bash
   python manage.py migrate
   python manage.py runserver
```
5. **Commit your changes** with clear messages:
```bash
   git commit -m "feat: add freelancer search/filter functionality"
```
6. **Push to your fork** and **open a Pull Request**, describing the change.

For larger features (e.g., messaging between clients and freelancers, payment integration, search/filtering), please open an **Issue** first to discuss the approach.

## To-do

- [ ] Add a proper repository description on GitHub summarizing the project's purpose.
- [ ] Clarify the purpose of `packges.txt` — merge its contents into `requirements.txt` if it lists Python dependencies, or rename/document it if it serves a different purpose (e.g., npm packages).
- [ ] Remove committed database/temp artifacts from version control: `db.sqlite3` and the stray `$RATJDLW.sqlite3` file appear to be local development artifacts and should generally be excluded via `.gitignore` rather than committed.
- [ ] Add a `.env`/settings separation for `SECRET_KEY`, `DEBUG`, and `ALLOWED_HOSTS` instead of hardcoding them in `django_project/settings.py` (if currently hardcoded).
- [ ] Document the exact routes/pages available in `accounts/` and `freelancers/` (registration, login, profile CRUD, showcase listing, etc.).
- [ ] Add automated tests (`accounts/tests.py`, `freelancers/tests.py`) for authentication and profile management flows.
- [ ] Add search/filter/category functionality for browsing freelancers, if not already implemented.
- [ ] Add deployment instructions (e.g., Docker, Heroku, Render) for production hosting.

## License

All rights are reserved by the author by default.

---
