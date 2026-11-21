# FastAPI - Image and Video Sharing

A social media application for sharing images and videos. It uses **FastAPI** for the backend, **Streamlit** for the interface, **SQLite** for data storage, and **ImageKit** for media hosting.

## Features

- User registration and login
- JWT authentication
- Image and video uploads
- Captions for posts
- Chronological social feed
- ImageKit media delivery
- Post deletion by the post owner

## Tech Stack

- Python 3.13
- FastAPI
- Streamlit
- FastAPI Users
- SQLAlchemy and SQLite
- ImageKit
- uv

## Project Structure

```text
.
├── app/
│   ├── app.py       # API routes and application setup
│   ├── db.py        # Database engine and models
│   ├── images.py    # ImageKit configuration
│   ├── schemas.py   # Pydantic schemas
│   └── users.py     # Authentication configuration
├── frontend.py      # Streamlit interface
├── main.py          # Backend entry point
├── pyproject.toml   # Project dependencies
└── uv.lock          # Locked dependencies
```

## Prerequisites

- Python 3.13 or newer
- [uv](https://docs.astral.sh/uv/) package manager
- An [ImageKit](https://imagekit.io/) account

## Installation

1. Clone the repository:

```bash
git clone https://github.com/hrishikesh-kakade/FastAPI-vid.img-sharing.git
cd FastAPI-vid.img-sharing
```

2. Install dependencies:

```bash
uv sync
```

3. Create a `.env` file in the project root:

```env
IMAGEKIT_PRIVATE_KEY=your_private_key
IMAGEKIT_PUBLIC_KEY=your_public_key
IMAGEKIT_URL=https://ik.imagekit.io/your_imagekit_id
```

## Running the Application

Start the FastAPI backend:

```bash
uv run python main.py
```

The API will run at `http://localhost:8000`.

API documentation is available at:

- Swagger UI: `http://localhost:8000/docs`
- ReDoc: `http://localhost:8000/redoc`

In a separate terminal, start the Streamlit frontend:

```bash
uv run streamlit run frontend.py
```

Open `http://localhost:8501` in your browser.

## Usage

1. Register an account or log in.
2. Open the **Upload** page.
3. Choose an image or video and add an optional caption.
4. Share the post.
5. View posts in the feed.
6. Delete posts that belong to your account.

## API Endpoints

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/auth/register` | Register a user |
| `POST` | `/auth/jwt/login` | Log in and receive a JWT |
| `GET` | `/users/me` | Get the authenticated user |
| `POST` | `/upload` | Upload media and create a post |
| `GET` | `/feed` | Get posts |
| `DELETE` | `/posts/{post_id}` | Delete an owned post |
