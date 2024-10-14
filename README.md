# URL Shortener(Long URL -- Short URL)

## Description

This URL Shortener is a web application that converts long URLs into short, shareable links, efficiently redirecting users to the original destination. It simplifies managing lengthy URLs in digital communications.
## Features of this URL Shortener

- Shorten long URLs through an API
- Store URL mappings in a MongoDB database
- Redirect users to the original URL when visiting the shortened link
- A React.js frontend where users can submit URLs and receive shortened versions

## Tech Stack

- **Backend**: Node.js, Express.js, and MongoDB for storing URL mappings
- **Frontend**: React.js for a user-friendly interface to shorten URLs and display results
- **Database**: MongoDB (can be replaced with SQLite if needed)

## files and Folders of the Project Structure

```
url-shortener
├── backend/                # Express.js backend API
│   ├── models/             # Mongoose models schema for storing URL mappings
│   ├── routes/             # API routes for handling URL shortening and redirection
│   ├── .env                # Environment variables
│   └── app.js              # Express server setup, Database and other configurations
├── frontend/               # React.js frontend app
│   ├── public/             # Static assets
│   ├── src/                # React components and logic
│   │   ├── components/     # Input form, shortened URL display, etc.
│   └── App.js              # Main React app component
├── README.md               # Project documentation
└── package.json            # Project dependencies and scripts
```

## Prerequisites of this project

- Node.js (v14+)
- npm
- MongoDB

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/url-shortener.git
   cd url-shortener
   ```

2. Backend Setup:
   - Navigate to the backend folder and install dependencies:
     ```bash
     cd backend
     npm install
     ```
   - Create a `.env` file for the backend configuration:
     ```env
     MONGO_URI=mongodb://localhost:27017/urlshortener
     BASE_URL=http://localhost:5000
     ```
   - Start the backend server:
     ```bash
     node app.js
     ```

3. Frontend Setup:
   - Navigate to the frontend folder and install dependencies:
     ```bash
     cd ../frontend
     npm install
     ```
   - Start the React development server:
     ```bash
     npm start
     ```
   - The frontend will be served at http://localhost:3000 by default.

## Usage

1. Open the React.js frontend in your browser by visiting http://localhost:3000.
2. Enter a long URL in the input field and click "Shorten".
3. The shortened URL will appear. When clicked, you will be redirected to the original long URL.
4. You can access shortened URLs directly in your browser by entering http://localhost:5000/<shortened_code>.

## API Endpoints

- `POST /api/shorten`: Create a shortened URL for a long URL.
  ```bash
  curl -X POST http://localhost:5000/api/shorten -H "Content-Type: application/json" -d '{"longUrl": "https://example.com"}'
  ```

- `GET /<code>`: Redirect to the original long URL using the shortened code.
  Example: `http://localhost:5000/abc123` will redirect to the corresponding long URL.

## Database Configuration(MongoDB)

If using MongoDB, ensure that your MongoDB instance is running locally or configure the database connection string in the `.env` file.


