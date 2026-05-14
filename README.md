# Weather App Backend

This project uses Node.js, Express.js, and PostgreSQL for the weather app pages:

- `index.html`
- `search.html`
- `world.html`

## Setup

1. Install PostgreSQL and create the database:

   ```bash
   psql -U postgres -f db/schema.sql
   ```

2. Install Node dependencies:

   ```bash
   npm install
   ```

3. Create `.env` from `.env.example` and update the values:

   ```bash
   PORT=3000
   OPENWEATHER_API_KEY=your_openweathermap_api_key
   DATABASE_URL=postgres://postgres:your_password@localhost:5432/weather_app
   ```

4. Start the server:

   ```bash
   npm start
   ```

To add many cities at once, edit `data/cities.json` and run:

```bash
npm run seed:cities
```

5. Open the app:

   ```text
   http://localhost:3000
   ```

## API

- `GET /api/health`
- `GET /api/weather/current?city=Mumbai`
- `GET /api/weather/forecast?city=Mumbai`
- `GET /api/weather/location?lat=19.076&lon=72.8777`
- `GET /api/cities`
- `POST /api/cities` with JSON body `{ "city": "Mumbai" }`
- `POST /api/cities/bulk` with JSON body `{ "cities": ["Mumbai,IN", "Delhi,IN"] }`
- `DELETE /api/cities/:id`
