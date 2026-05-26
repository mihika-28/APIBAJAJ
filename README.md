# BFHL API — Acropolis Campus Hiring (May 2026)

**Student:** Mihika Sharma  
**Roll No:** 0827CS243D12  
**Email:** mihikasharma241280@acropolis.in

---

## Tech Stack
- Java 17
- Spring Boot 3.2.5
- Maven

---

## Project Structure

```
src/
├── main/java/com/mihika/bfhl/
│   ├── BfhlApplication.java          ← Entry point
│   ├── controller/
│   │   └── BfhlController.java       ← POST /bfhl
│   ├── service/
│   │   ├── BfhlService.java          ← Interface
│   │   └── BfhlServiceImpl.java      ← Business logic
│   ├── dto/
│   │   ├── BfhlRequestDto.java       ← Request DTO
│   │   ├── BfhlResponseDto.java      ← Response DTO
│   │   └── ErrorResponseDto.java     ← Error DTO
│   └── exception/
│       └── GlobalExceptionHandler.java
└── test/java/com/mihika/bfhl/
    └── BfhlApplicationTests.java     ← 11 test cases
```

---

## Running Locally

```bash
# Build
mvn clean package

# Run
java -jar target/bfhl-1.0.0.jar

# Test
curl -X POST http://localhost:8080/bfhl \
  -H "Content-Type: application/json" \
  -d '{"data": ["a", "1", "334", "4", "R", "$"]}'
```

---

## API Reference

### POST /bfhl

**Request:**
```json
{
  "data": ["a", "1", "334", "4", "R", "$"]
}
```

**Response (200 OK):**
```json
{
  "is_success": true,
  "user_id": "mihika_sharma_28102005",
  "email": "mihikasharma241280@acropolis.in",
  "roll_number": "0827CS243D12",
  "odd_numbers": ["1"],
  "even_numbers": ["334", "4"],
  "alphabets": ["A", "R"],
  "special_characters": ["$"],
  "sum": "339",
  "concat_string": "Ra"
}
```

---

## Deploying to Render

1. Push this repo to GitHub.
2. Go to [render.com](https://render.com) → New → Web Service.
3. Connect your GitHub repo.
4. Render will auto-detect `render.yaml`.
5. Deploy — your URL will be `https://<name>.onrender.com/bfhl`.

## Deploying to Railway

1. Push this repo to GitHub.
2. Go to [railway.app](https://railway.app) → New Project → Deploy from GitHub.
3. Railway uses `railway.toml` automatically.
4. Your URL will be `https://<name>.up.railway.app/bfhl`.

---

## Running Tests

```bash
mvn test
```

11 test cases covering:
- All 3 provided examples (A, B, C)
- Empty data array
- Only special characters
- Zero as even number
- Single letter concat
- Numbers returned as strings
- HTTP 400 on missing data field
- HTTP 400 on malformed JSON
- HTTP 200 on empty array
