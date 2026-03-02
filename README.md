# LeilaoExpress

A JavaFX desktop application for managing auctions. The app supports user authentication, auction creation and participation, bid handling, categories, client management, points/credits, and automated bidding agents, all backed by a SQL Server database.

## Features
- Login and registration flow
- Create, edit, list, and close auctions
- Bidding and auction participation
- Categories and auction classification (ratings)
- Client management and approval workflow
- Points/credits management
- Automatic bidding agents
- CSV import support
- Email notifications (e.g., inactivity, credits, auction win)

## Tech Stack
- Java 21
- JavaFX 21 (FXML)
- Maven (with Maven Wrapper)
- SQL Server (via HikariCP)
- Dotenv for DB config
- JavaMail + Mailjet client (email)

## Project Structure
- `LP2/` JavaFX application module
- `LP2/src/main/java/com/lp2/lp2/Controller/` UI controllers
- `LP2/src/main/java/com/lp2/lp2/Service/` Business logic
- `LP2/src/main/java/com/lp2/lp2/DAO/` Data access layer
- `LP2/src/main/java/com/lp2/lp2/Model/` Domain models
- `LP2/src/main/resources/com/lp3_grupo5/lp2/` FXML views and styles
- `DB/DbScript.sql` SQL Server schema and seed data
- `docs/` diagrams and use-case artifacts

## Database
The application expects a SQL Server database. The default schema and seed data are provided in `DB/DbScript.sql`.

### Environment Variables
Create a `.env` file inside `LP2/` with the following keys:

```env
DB_URL=jdbc:sqlserver://localhost:1433;databaseName=Leiloeira;encrypt=true;trustServerCertificate=true
DB_USER=sa
DB_PASSWORD=your_password
```

### Docker (Optional)
A sample SQL Server Docker Compose file is available at:
`LP2/src/main/java/com/lp2/lp2/Util/docker-compose.yml`

Start SQL Server with:

```bash
docker compose -f LP2/src/main/java/com/lp2/lp2/Util/docker-compose.yml up -d
```

Then load the schema from `DB/DbScript.sql`.

## Run Locally
Prerequisites:
- JDK 21
- SQL Server running with the schema loaded

From the repository root:

```bash
cd LP2
./mvnw clean javafx:run
```

On Windows:

```bat
cd LP2
mvnw.cmd clean javafx:run
```

## Notes
- The app starts at the login screen (`Login.fxml`).
- Email notifications use Gmail SMTP in `LP2/src/main/java/com/lp2/lp2/Util/GmailSender.java` and currently require valid credentials.

## License
Not specified.
