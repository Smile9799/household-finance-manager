# Household Finance Manager

A comprehensive personal and household financial management system designed to help families track their budgets, manage debts, monitor investments, and handle shared expenses efficiently.

## 🏠 Overview

This system provides a complete solution for household financial management including:

- **Debt Tracking**: Monitor multiple debts with payment history and balance calculations
- **Investment Management**: Track contributions and performance across multiple investment accounts
- **Budget Management**: Categorize expenses and track monthly spending patterns
- **Shopping Lists**: Convert monthly shopping plans into actual transactions
- **Shared Expenses**: Manage group expenses with automatic splitting and balance tracking
- **Document Management**: Attach receipts and documents to transactions

## 🏗️ Architecture

- **Backend**: Java REST API with Spring Boot
- **Database**: Oracle Database 12c+
- **Frontend**: Android Application (Java)
- **Deployment**: Self-hosted

## 📱 Features

### Debt Management
- Track multiple debt types (home loans, credit cards, personal loans)
- Manual balance updates with override capabilities
- Payment history tracking
- Remaining balance calculations

### Investment Tracking
- Multiple investment account support (TFSA, RA, etc.)
- Contribution split management across underlying assets
- Monthly performance tracking
- Contribution history

### Budget & Expenses
- Predefined expense categories (food, insurance, utilities, etc.)
- Monthly shopping list management
- Transaction categorization
- Receipt and document attachments

### Shared Expenses
- Group expense management
- Equal and custom expense splitting
- Balance tracking between users
- Outstanding payment reminders

## 🚀 Getting Started

### Prerequisites

- Java 11+ (LTS recommended)
- Oracle Database 12c or higher
- Android Studio for mobile development
- Maven or Gradle for dependency management

### Backend Setup

1. Clone the repository:
```bash
git clone https://github.com/yourusername/household-finance-manager.git
cd household-finance-manager
```

2. Configure Oracle Database connection in `application.properties`:
```properties
spring.datasource.url=jdbc:oracle:thin:@localhost:1521:XE
spring.datasource.username=your_username
spring.datasource.password=your_password
```

3. Run the application:
```bash
./mvnw spring-boot:run
```

### Android App Setup

1. Open the `android-app` directory in Android Studio
2. Configure API endpoint in `ApiConfig.java`
3. Build and run on your Android device

### Database Setup

1. Create Oracle Database schema using provided SQL scripts:
```bash
sqlplus username/password@database @scripts/create_schema.sql
```

2. Run initial data migration:
```bash
./mvnw flyway:migrate
```

## 📊 Supported Financial Categories

### Debts
- Debt review
- Home loan
- Car loan
- Credit cards (Absa, etc.)
- Personal loans
- Store cards

### Expenses
- Food & Groceries
- Insurance (multiple policies)
- Municipal levies
- Body corporate fees
- Fuel
- Home maintenance

### Investments
- Tax-Free Savings Account (TFSA)
- Retirement Annuity (RA)
- General investment accounts
- Underlying asset allocation tracking

### Shared Expenses
- Utilities (electricity, water)
- Subscriptions (streaming services, cloud storage)
- Household supplies

## 🛠️ Technology Stack

### Backend
- **Framework**: Spring Boot 2.7+
- **Database**: Oracle Database 12c+
- **ORM**: Hibernate/JPA
- **Security**: Spring Security with JWT
- **Documentation**: Swagger/OpenAPI 3.0
- **Build Tool**: Maven

### Android Application
- **Language**: Java
- **Min SDK**: API 21 (Android 5.0+)
- **Architecture**: MVVM pattern
- **Local Storage**: Room Database
- **HTTP Client**: Retrofit
- **Authentication**: JWT tokens

### Database
- **Primary**: Oracle Database
- **Connection Pool**: HikariCP
- **Migrations**: Flyway
- **Backup**: Automated daily backups

## 📁 Project Structure

```
household-finance-manager/
├── backend/                 # Java Spring Boot API
│   ├── src/main/java/
│   ├── src/main/resources/
│   └── pom.xml
├── android-app/            # Android application
│   ├── app/src/main/java/
│   ├── app/src/main/res/
│   └── build.gradle
├── database/               # Database scripts
│   ├── migrations/
│   └── schema/
├── docs/                   # Documentation
│   ├── api/
│   └── requirements/
└── README.md
```

## 🔧 Configuration

### Environment Variables

```bash
# Database Configuration
DB_HOST=localhost
DB_PORT=1521
DB_NAME=XE
DB_USERNAME=finance_user
DB_PASSWORD=your_secure_password

# Application Configuration
JWT_SECRET=your_jwt_secret_key
FILE_UPLOAD_PATH=/path/to/file/storage
MAX_FILE_SIZE=10MB
```

### Application Properties

Key configuration options in `application.properties`:

```properties
# Server Configuration
server.port=8080

# Database Configuration
spring.datasource.driver-class-name=oracle.jdbc.OracleDriver
spring.jpa.database-platform=org.hibernate.dialect.Oracle12cDialect

# File Upload Configuration
spring.servlet.multipart.max-file-size=10MB
spring.servlet.multipart.max-request-size=10MB

# Security Configuration
jwt.expiration=86400
```

## 🧪 Testing

### Backend Tests
```bash
./mvnw test
```

### Android Tests
```bash
./gradlew test
./gradlew connectedAndroidTest
```

## 📖 API Documentation

Once the backend is running, API documentation is available at:
- Swagger UI: `http://localhost:8080/swagger-ui.html`
- OpenAPI JSON: `http://localhost:8080/api-docs`

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🛡️ Security

- All financial data is encrypted at rest
- API communications use HTTPS/TLS
- JWT-based authentication
- Role-based access control
- File upload validation and scanning

## 📞 Support

For support and questions:
- Create an issue in this repository
- Check the [documentation](docs/) folder
- Review the API documentation

## 🗺️ Roadmap

- [ ] Basic debt and expense tracking
- [ ] Investment management
- [ ] Shared expense functionality
- [ ] Android application
- [ ] Document attachment system
- [ ] Reporting and analytics
- [ ] Performance optimization
- [ ] Advanced budgeting features

## ⚠️ Disclaimer

This software is for personal financial tracking purposes. Always consult with financial professionals for important financial decisions. The developers are not responsible for any financial losses or decisions made based on this software.
