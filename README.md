# VetCare Management System

A modern veterinary clinic management application built with Spring Boot, designed to streamline pet healthcare operations.

## Features

- **Pet Management**: Register and manage pet profiles with medical history
- **Owner Management**: Maintain comprehensive owner information and contact details
- **Veterinarian Portal**: Manage veterinary staff and their specializations
- **Appointment Scheduling**: Book and track veterinary appointments
- **Medical Records**: Digital health records and treatment history
- **Multi-Database Support**: H2 (development), MySQL, PostgreSQL

## Tech Stack

- **Backend**: Spring Boot 3.x, Spring MVC, Spring Data JPA
- **Frontend**: Thymeleaf, Bootstrap, HTML5/CSS3
- **Database**: H2 (default), MySQL, PostgreSQL
- **Build Tools**: Maven, Gradle
- **Java Version**: 17+

## Quick Start

### Prerequisites
- Java 17 or higher
- Maven or Gradle

### Installation

1. Clone the repository:
```bash
git clone <your-repo-url>
cd spring-petclinic
```

2. Run with Maven:
```bash
./mvnw spring-boot:run
```

Or with Gradle:
```bash
./gradlew bootRun
```

3. Access the application at `http://localhost:8080`

## Database Configuration

### Default (H2)
- Console: `http://localhost:8080/h2-console`
- JDBC URL: `jdbc:h2:mem:<uuid>` (check console logs for UUID)

### MySQL
```bash
docker run -e MYSQL_USER=petclinic -e MYSQL_PASSWORD=petclinic -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=petclinic -p 3306:3306 mysql:9.5
```
Run with: `--spring.profiles.active=mysql`

### PostgreSQL
```bash
docker run -e POSTGRES_USER=petclinic -e POSTGRES_PASSWORD=petclinic -e POSTGRES_DB=petclinic -p 5432:5432 postgres:18.1
```
Run with: `--spring.profiles.active=postgres`

## Docker Support

Build container image:
```bash
./mvnw spring-boot:build-image
```

Use Docker Compose:
```bash
docker compose up mysql
# or
docker compose up postgres
```

## Development

### IDE Setup
- Import as Maven/Gradle project
- Ensure Java 17+ is configured
- Run `PetClinicApplication.main()` method

### CSS Compilation
```bash
./mvnw package -P css
```

## Project Structure

```
src/
├── main/
│   ├── java/org/springframework/samples/petclinic/
│   │   ├── model/          # Entity classes
│   │   ├── repository/     # Data access layer
│   │   ├── service/        # Business logic
│   │   ├── web/           # Controllers
│   │   └── system/        # Configuration
│   └── resources/
│       ├── static/        # CSS, JS, images
│       ├── templates/     # Thymeleaf templates
│       └── db/           # Database scripts
└── test/                 # Test classes
```

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the Apache License 2.0 - see the [LICENSE.txt](LICENSE.txt) file for details.

## Contact

For questions or support, please open an issue in the repository.