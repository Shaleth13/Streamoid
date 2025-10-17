# Streamoid
# Product Upload & Search API

This FastAPI application allows uploading product data from a CSV file, validates it, stores it in SQLite and supports listing and searching.

## Features
- Upload CSV file with validation rules:
  - price ≤ MRP
  - quantity ≥ 0
  - required fields: sku, name, brand, mrp, price
- Store valid rows in SQLite
- `/products` — list all products with pagination
- `/products/search` — filter by brand, color, or price range

## Tech Stack
- FastAPI (Python)
- SQLite
- Pandas
- Ngrok (for Colab deployment)

## Run in Colab
1. Open the notebook in Google Colab.
2. Run all cells to install dependencies and start the FastAPI server.
3. Copy the ngrok URL shown (for example, `https://xyz.ngrok-free.dev`).
4. Open `<ngrok-url>/docs` to interact with the API.

## Example curl
curl -X POST -F "file=@products.csv" https://xyz.ngrok-free.dev/upload

curl "https://xyz.ngrok-free.dev/products?page=1&limit=10
"
curl "https://xyz.ngrok-free.dev/products/search?brand=StreamThreads&maxPrice=1000
"
