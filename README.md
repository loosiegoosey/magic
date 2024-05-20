# Magic: The Gathering Deck Builder

## Overview

The Magic: The Gathering Deck Builder project is a Django-based web application designed to help users create, manage, and visualize Magic: The Gathering card decks. The project allows users to add cards and decks, view details of cards, and manage their collection efficiently.

## Features

- **User-friendly Interface**: Simple and clean web interface to manage cards and decks.
- **Card Management**: Add, update, and delete cards with detailed information like title, mana cost, type, rules, etc.
- **Deck Management**: Create and manage custom decks, including adding or removing cards from decks.
- **Admin Panel**: Administrative interface for managing cards and decks using Django's admin framework.
- **Data Gathering**: Scripts to fetch and update card data from external sources.
- **Database Interaction**: Backend SQL database management using SQLite.
- **Automated Testing**: Unit tests to ensure the application's functionality.

## Installation Instructions

Follow the steps below to set up the project on your local machine:

1. **Clone the repository**:
    ```bash
    git clone https://github.com/Yuriy/magic.git
    cd magic/djangoproject
    ```

2. **Set up a virtual environment** (optional but recommended):
    ```bash
    python3 -m venv env
    source env/bin/activate
    ```

3. **Install required dependencies**:
    ```bash
    pip install -r requirements.txt
    ```

4. **Set up the database**:
    ```bash
    python manage.py migrate
    python manage.py createsuperuser  # Follow the prompts to create a superuser account
    ```

5. **Run the development server**:
    ```bash
    python manage.py runserver
    ```

6. **Access the web application**:
    Open your web browser and navigate to `http://127.0.0.1:8000/`.

## Usage Examples

### Adding a Card

- **Admin Panel**:
  1. Navigate to `http://127.0.0.1:8000/admin/`.
  2. Log in with your superuser account.
  3. Go to `Magic > Cards > Add card`.
  4. Fill in the card details and save.

### Viewing Decks

- **Home Page**:
  1. Open `http://127.0.0.1:8000/`.
  2. Click on the "Magic" section to view available decks.
  3. Select a deck to see its details and cards.

### Usage in Code

```python
from djangoproject.magic.models import Card

# Create a new card
card = Card.objects.create(
    title="Serra Angel",
    manaCost="3WW",
    convertedManaCost=5,
    type="Creature — Angel",
    rules="Flying, vigilance",
    cardSet="Core Set 2021",
    rarity="Rare"
)
print(f"Added card: {card.title}")
```

## Code Summary

The project is organized into several key files and directories:

- `djangoproject/manage.py`: The script for interacting with the Django project.
- `djangoproject/settings.py`: Configuration settings for the Django project.
- `djangoproject/urls.py`: URL routing for the Django project.
- `djangoproject/views.py`: Views for rendering templates.
- `djangoproject/magic`: Django app for Magic: The Gathering functionalities.
  - `admin.py`: Configures the Django admin interface.
  - `models.py`: Defines the database models for cards and decks.
  - `views.py`: Application views to handle requests and render responses.
  - `urls.py`: URL routing for the `magic` app.
  - `tests.py`: Unit tests for the app.
- `media/`: Directory containing static media files like JavaScript libraries.
- `magic/`: Directory with various scripts for database creation, data gathering, and utility scripts.

## Contributing Guidelines

We welcome contributions to improve the project! Please follow these steps to contribute:

1. **Fork the repository**:
   - Click on the "Fork" button on the top right of the repository page.

2. **Clone the forked repository**:
   ```bash
   git clone https://github.com/your-username/magic.git
   cd magic
   ```

3. **Create a new branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```

4. **Make your changes and commit**:
   ```bash
   git add .
   git commit -m "Add your commit message here"
   ```

5. **Push to your forked repository**:
   ```bash
   git push origin feature/your-feature-name
   ```

6. **Open a Pull Request**:
   - Go to your forked repository on GitHub.
   - Click on the "New Pull Request" button and follow the instructions.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
