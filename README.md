### API Overview

The MoviesDatabase API provides access to comprehensive and up-to-date data for over 9 million titles, including movies, TV series, and episodes, as well as information on over 11 million actors, crew members, and cast. This API allows developers to retrieve detailed information about movies and TV shows, including cast, plot, genres, and IMDb ratings. It also offers features like movie recommendations and search capabilities by actor or director.


### Version

The current version of the MoviesDatabase API is v1.


### Available Endpoints

  - /titles: Fetches a list of movies or TV shows. Supports filtering by year, genre, and pagination.
  - /titles/{id}: Retrieves detailed information about a specific movie or TV show by its unique ID.
  - /actors: Returns information about actors, including their biography, filmography, and other details.
  - /genres: Lists all available genres for filtering movie and TV show searches.


### Request and Response Format

### Request Format

  - Method: GET
  - Headers:
      - x-api-key: Your API key (provided upon subscription)
  - Query Parameters (for /titles endpoint):
      - year: Filter by release year.
      - genre: Filter by genre.
      - page: Specify the page number for pagination.

### Example Request

### Response Format

  - Content-Type: application/json
  - Status Codes:
      - 200 OK: Successful request.
      - 401 Unauthorized: Missing or invalid API key.
      - 404 Not Found: Resource not found.
      - 429 Too Many Requests: Rate limit exceeded.

### Example Response

```json
{
  "page": 2,
  "results": [
    {
      "id": "tt1234567",
      "title": "Action Movie",
      "year": 2023,
      "genre": ["Action", "Adventure"],
      "rating": 7.8
    }
  ]
}


### Authentication

To authenticate your requests, include the x-api-key header with your API key in each request. The API key is provided upon subscription to the MoviesDatabase API on RapidAPI.

### Error Handling

401 Unauthorized: Ensure that your x-api-key is included and valid.

404 Not Found: Verify that the requested resource exists.

429 Too Many Requests: Implement rate limiting in your application to avoid exceeding the API's usage limits.

### Usage Limits and Best Practices

Rate Limit: The API has a rate limit of 1000 requests per hour.

Pagination: Use the page query parameter to paginate through large datasets.

Caching: Implement caching mechanisms to reduce the number of API calls and improve performance.

Secure API Key: Never expose your API key in client-side code; use server-side requests to keep your key safe.