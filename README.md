URL Shortener API - Golang

📌 Description

This is a high-performance and scalable URL shortener API built with Golang. It uses Fiber for the web framework, Gorm for database management (PostgreSQL), and Redis for caching to improve speed and efficiency.

🚀 Features

Shorten long URLs into unique short links

Redirect users from short URLs to their original URLs

Uses Redis for fast lookup and caching

Database persistence using PostgreSQL

RESTful API with JSON responses

🛠️ Installation

1. Clone the Repository

git clone https://github.com/yourusername/url-shortener-api.git
cd url-shortener-api

2. Install Dependencies

Make sure you have Go installed, then run:

go mod tidy

3. Set Up Environment Variables

Create a .env file in the root directory and add the following:

PORT=8080
DATABASE_URL=postgres://username:password@localhost:5432/urlshortener
REDIS_ADDR=localhost:6379

4. Run the Database (PostgreSQL)

If you don't have PostgreSQL installed, you can use Docker:

docker run --name urlshortener-db -e POSTGRES_USER=username -e POSTGRES_PASSWORD=password -e POSTGRES_DB=urlshortener -p 5432:5432 -d postgres

5. Run Redis (Optional but Recommended)

docker run --name redis-server -p 6379:6379 -d redis

6. Run the Application

go run main.go

📡 API Endpoints

1️⃣ Shorten a URL

POST /api/shorten

Request Body:

{
  "url": "https://example.com/long-url"
}

Response:

{
  "short_url": "abc12345"
}

2️⃣ Redirect to Original URL

GET /{short_url}

Example:

curl -L http://localhost:8080/abc12345

📜 License

This project is open-source and available under the MIT License.

🙌 Contributing

Feel free to fork and submit pull requests!

