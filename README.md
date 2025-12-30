# Configure JWT with Spring Boot and Custom Json Swagger UI

1. Configure JWT with Spring Boot and Custom Json Swagger UI<br/>
2. Dynamic Jxls Excel import & export
3. Json Schema Generator & validations
4. Dynamic Api creations

---

## Quick start

- Run the application from your IDE or via Maven/Gradle as a Spring Boot app.
- The application reads configuration from `src/main/resources/application.properties`.

## Important runtime defaults (from application.properties)

- Server port: `9091` (property: `server.port=9091`)
- H2 console: http://localhost:9091/h2-console/ (in-memory DB)
  - JDBC URL: `jdbc:h2:mem:testdb`
  - Username: `sa`
  - Password: `password`
- Default API base URL shown in the UI: `http://localhost:9091/api` (this is displayed in `index.jsp`)

## Swagger UI / API docs

- Swagger UI assets are served from `/static/swagger/` and the JSP views that bootstrap Swagger are:
  - `src/main/webapp/WEB-INF/views/index.jsp`
  - `src/main/webapp/WEB-INF/views/swagger.jsp`

- Both JSPs load the default Swagger JSON at `/static/swagger/app.json` unless a `url` query parameter is provided. If you need to point the UI to a different swagger JSON, pass `?url=<your-json-url>` in the page URL.

## JWT configuration

- The application uses the following JWT-related properties (see `application.properties`):
  - `app.jwt.secret` — the signing secret used by the application (default value in repo is `======================javamahendra===========================`).
  - `app.jwt.time` — token time in milliseconds (default set to `86400000` in the repository, i.e. 24h).

Be sure to override these values in production with secure/unique secrets and appropriate token lifetimes.

## JSON schema / token generation

- The project contains schema files under `src/main/resources/schema/` (for example `generatetoken.json`). The property `Generate_Token_v1_0_SCHEMA` in `application.properties` points to `generatetoken.json` by default.

## Notes

- The README previously listed high-level features; this update adds basic runtime and configuration details (server port, H2 console, JWT property names, and Swagger JSON location) to match the current code and resource layout.

