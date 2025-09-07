Angular .Net core app
A comprehensive App built with ASP.NET Core 8 API and Angular 20 frontend.

Features
User Authentication & Authorization: JWT-based authentication with role-based access control
Asset Management: Complete CRUD operations for assets with assignment tracking
User Management: Admin-only user management functionality
Asset History: Track all changes and assignments to assets
Maintenance Records: Schedule and track maintenance activities
Modern UI: Angular Material design with responsive layout
Real-time Updates: Reactive data management with RxJS
Technology Stack
Backend
ASP.NET Core 8: Modern web framework
Entity Framework Core: ORM for database operations
SQL Server: Database (LocalDB for development)
JWT Authentication: Secure token-based authentication
AutoMapper: Object mapping between models and DTOs
Swagger: API documentation
Frontend
Angular 20: Modern frontend framework
Angular Material: UI component library
RxJS: Reactive programming
TypeScript: Type-safe JavaScript
Prerequisites
.NET 8 SDK
Node.js 18+ and npm
SQL Server LocalDB (included with Visual Studio)
Visual Studio 2022 or VS Code
Setup Instructions
1. Clone the Repository
git clone <repository-url>
cd AMS
2. Backend Setup
Navigate to the API project:

cd AMS.Api
Restore NuGet packages:

dotnet restore
Update database (creates the database and applies migrations):

dotnet ef database update
Run the API:

dotnet run
The API will be available at https://localhost:7001

3. Frontend Setup
Navigate to the frontend project:

cd ams-frontend
Install dependencies:

npm install
Run the development server:

npm start
The frontend will be available at http://localhost:4200

Default Credentials
The system comes with a default admin user:

Username: admin
Password: Admin123!
API Endpoints
Authentication
POST /api/auth/login - User login
Users (Admin only)
GET /api/users - Get all users
GET /api/users/{id} - Get user by ID
POST /api/users - Create new user
PUT /api/users/{id} - Update user
DELETE /api/users/{id} - Delete user
Assets
GET /api/assets - Get all assets (with optional filtering)
GET /api/assets/{id} - Get asset by ID
POST /api/assets - Create new asset
PUT /api/assets/{id} - Update asset
DELETE /api/assets/{id} - Delete asset
POST /api/assets/{id}/assign - Assign asset to user
POST /api/assets/{id}/unassign - Unassign asset
GET /api/assets/categories - Get asset categories
GET /api/assets/locations - Get asset locations
Database Schema
Users
User authentication and profile information
Role-based access control (Admin, Manager, User)
Assets
Asset information including name, category, brand, model
Status tracking (Available, Assigned, Maintenance, Retired)
Assignment to users
Location and condition tracking
AssetHistory
Complete audit trail of asset changes
Assignment/unassignment history
Status change tracking
MaintenanceRecords
Scheduled and completed maintenance
Cost tracking
Maintenance type classification
Development
Adding New Features
Backend: Add models, DTOs, services, and controllers
Frontend: Add components, services, and routing
Database: Create migrations for schema changes
Code Structure
AMS/
├── AMS.Api/                 # Backend API
│   ├── Controllers/         # API endpoints
│   ├── Data/               # Database context
│   ├── DTOs/               # Data transfer objects
│   ├── Models/             # Entity models
│   ├── Services/           # Business logic
│   └── Mapping/            # AutoMapper profiles
├── ams-frontend/           # Frontend application
│   ├── src/
│   │   ├── app/
│   │   │   ├── components/ # Reusable components
│   │   │   ├── models/     # TypeScript interfaces
│   │   │   ├── pages/      # Page components
│   │   │   ├── services/   # API services
│   │   │   └── guards/     # Route guards
│   │   └── environments/   # Environment configuration
└── README.md
Deployment
Backend Deployment
Build the application: dotnet publish -c Release
Deploy to your hosting platform (Azure, AWS, etc.)
Configure connection strings and environment variables
Frontend Deployment
Build the application: ng build --configuration production
Deploy the dist folder to your web server
Update the API URL in environment configuration
Contributing
Fork the repository
Create a feature branch
Make your changes
Add tests if applicable
Submit a pull request
