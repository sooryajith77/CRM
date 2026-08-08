# CRM System – Customer Relationship Management

## Overview

CRM System is a full-stack Customer Relationship Management application designed to help users manage customer relationships and business activities through a centralized platform.

The application provides authentication, role-based access, lead management, company management, deal management, ticket management, file uploads, notifications, and communication features.

## Technology Stack

### Frontend

- React.js
- HTML5
- CSS3
- JavaScript
- React-Toastify

### Backend

- Node.js
- Express.js
- REST APIs

### Database

- PostgreSQL

### Authentication

- JWT (JSON Web Token)

### Additional Technologies

- Multer – File and image uploads
- Nodemailer – Email notifications
- Twilio – SMS, calls, and OTP verification
- React-Toastify – Frontend notifications
- Postman – API testing
- Git & GitHub – Version control

---

## Features

### Authentication

- User registration
- User login
- JWT-based authentication
- Protected routes
- Role-based access control
- Secure access to protected resources

### Lead Management

The Lead Management module allows users to manage and track potential customers.

Features include:

- Create leads
- View leads
- Update lead information
- Track lead status
- Manage lead-related information

### Company Management

The Company Management module allows users to manage company and customer information.

Features include:

- Create company records
- View company information
- Update company information
- Manage company-related data

### Deal Management

The Deal Management module helps users manage business opportunities and track their progress.

Features include:

- Create deals
- View deals
- Update deals
- Track deal status
- Pipeline tracking
- Manage deal information

### Ticket Management

The Ticket Management module allows users to manage support and service requests.

Features include:

- Create tickets
- View tickets
- Update tickets
- Track ticket status
- Manage ticket information

### File and Image Uploads

The application supports file and image uploads using **Multer**.

Uploaded files can be processed by the backend and associated with relevant CRM records.

### Email Notifications

**Nodemailer** is used to provide email-based notification functionality.

The application can send email notifications for supported CRM workflows and events.

### Twilio Integration

**Twilio** is integrated to provide communication functionality.

Supported functionality includes:

- SMS
- Phone calls
- OTP verification

### Frontend Notifications

**React-Toastify** is used to provide feedback to users through toast notifications.

Notifications can be used for:

- Successful operations
- Error messages
- Warnings
- Informational messages
- Authentication feedback
- Form submission feedback

---

## System Architecture

The CRM follows a client-server architecture.

```text
                         User
                           │
                           ▼
                  React Frontend
                           │
                           │ HTTP / REST API
                           ▼
                  Express.js Backend
                           │
             ┌─────────────┼─────────────┐
             │             │             │
             ▼             ▼             ▼
       Authentication   Business      File Uploads
          & JWT          Logic           Multer
             │             │
             └──────┬──────┘
                    │
                    ▼
              PostgreSQL
                Database
                    │
          ┌─────────┼─────────┐
          ▼         ▼         ▼
      Nodemailer  Twilio   API Response
          │         │         │
          ▼         ▼         ▼
       Email      SMS/Call   Frontend
                              │
                              ▼
                       React-Toastify
```

---

## Project Structure

```text
CRM/
│
├── frontend/
│   ├── src/
│   ├── components/
│   ├── pages/
│   ├── services/
│   └── assets/
│
├── backend/
│   ├── controllers/
│   ├── routes/
│   ├── middleware/
│   ├── models/
│   ├── services/
│   ├── config/
│   ├── uploads/
│   └── server.js
│
└── README.md
```

> Update the folder structure if the actual project uses different folder names.

---

# Authentication and Authorization

## JWT Authentication

The CRM uses **JSON Web Token (JWT)** authentication to secure protected resources.

### Authentication Flow

```text
User
 │
 │ Login credentials
 ▼
Frontend
 │
 │ Login request
 ▼
Backend
 │
 │ Validate credentials
 ▼
JWT Token
 │
 │ Return token
 ▼
Frontend
 │
 │ Store/use token
 ▼
Protected API Request
 │
 │ Authorization: Bearer <JWT_TOKEN>
 ▼
Backend
 │
 │ Verify JWT
 ▼
Protected Resource
```

### Authentication Process

1. The user enters their login credentials.
2. The frontend sends the credentials to the backend.
3. The backend validates the credentials.
4. A JWT is generated after successful authentication.
5. The token is returned to the client.
6. The client sends the token with protected requests.
7. The backend verifies the token.
8. The request is processed if authentication is valid.

## Role-Based Access Control

The CRM uses role-based access control to restrict access to specific resources and operations.

Authorized users can access functionality according to their assigned role.

---

# Lead Management

The Lead Management module helps users organize and track potential customers.

### Lead Operations

Users can:

- Create leads
- View leads
- Update leads
- Track lead status
- Manage lead information

### Lead Workflow

```text
New Lead
   │
   ▼
Lead Information
   │
   ▼
Lead Status Tracking
   │
   ▼
Follow-up
   │
   ▼
Potential Customer
```

---

# Company Management

The Company Management module allows users to maintain company-related information.

Users can:

- Create company records
- View company information
- Update company information
- Manage company records
- Associate CRM information with companies

---

# Deal Management

The Deal Management module allows users to manage business opportunities.

### Deal Features

- Create deals
- View deals
- Update deals
- Track deal status
- Pipeline tracking
- Manage deal information

### Deal Pipeline

```text
New Deal
   │
   ▼
Qualification
   │
   ▼
Negotiation
   │
   ▼
In Progress
   │
   ▼
Won / Lost
```

> The exact pipeline stages should match the stages implemented in the application.

---

# Ticket Management

The Ticket Management module is used to manage support and service requests.

Users can:

- Create tickets
- View tickets
- Update tickets
- Track ticket status
- Manage ticket information

### Ticket Workflow

```text
Ticket Created
      │
      ▼
   Open
      │
      ▼
 In Progress
      │
      ▼
 Resolved
      │
      ▼
  Closed
```

> The exact ticket statuses should match the implementation.

---

# File Uploads

The CRM uses **Multer** for handling file and image uploads.

### Upload Process

```text
User
 │
 ▼
Select File
 │
 ▼
Frontend
 │
 ▼
Backend API
 │
 ▼
Multer
 │
 ▼
File Processing
 │
 ▼
Stored File
```

Multer handles multipart form data submitted to the backend.

---

# Email Notifications

The CRM uses **Nodemailer** for email communication.

### Email Workflow

```text
CRM Event
    │
    ▼
Backend
    │
    ▼
Nodemailer
    │
    ▼
Email Service
    │
    ▼
Recipient
```

Nodemailer can be used for supported email notification workflows such as account-related or CRM activity notifications.

---

# Twilio Integration

The CRM uses **Twilio** for communication functionality.

### Supported Communication Features

- SMS
- Phone calls
- OTP verification

### OTP Workflow

```text
User
 │
 │ Request OTP
 ▼
Backend
 │
 ▼
Twilio
 │
 ▼
SMS
 │
 ▼
User receives OTP
 │
 ▼
User submits OTP
 │
 ▼
Backend verifies OTP
```

---

# Frontend Notifications

The CRM uses **React-Toastify** to display user-friendly notifications.

### Notification Types

- Success
- Error
- Warning
- Information

Example use cases:

```text
Successful Login
       ↓
Success Toast

Invalid Login
       ↓
Error Toast

Form Validation
       ↓
Warning Toast

API Response
       ↓
Information Toast
```

---

# REST API

The backend provides RESTful APIs for communication between the frontend and backend.

## HTTP Methods

| Method | Purpose |
|---|---|
| GET | Retrieve data |
| POST | Create data |
| PUT | Update existing data |
| PATCH | Partially update data |
| DELETE | Delete data |

## API Request

Protected API requests require a valid JWT.

Example:

```http
Authorization: Bearer <JWT_TOKEN>
```

## API Testing

API endpoints can be tested using **Postman**.

Testing should include:

- Registration
- Login
- Authentication
- Authorization
- Lead operations
- Company operations
- Deal operations
- Ticket operations
- File uploads
- Invalid requests
- Unauthorized requests
- Error responses

> Exact endpoint names and request/response examples should be documented from the active backend route definitions.

---

# Environment Variables

Sensitive configuration values should be stored in environment variables.

Example:

```env
DATABASE_URL=your_database_url
JWT_SECRET=your_jwt_secret
PORT=5000
```

If Twilio or email services require credentials, store those values in environment variables as well.

Example:

```env
TWILIO_ACCOUNT_SID=your_account_sid
TWILIO_AUTH_TOKEN=your_auth_token
TWILIO_PHONE_NUMBER=your_phone_number

EMAIL_HOST=your_email_host
EMAIL_PORT=your_email_port
EMAIL_USER=your_email
EMAIL_PASSWORD=your_password
```

> The exact environment variable names must match the application source code.

> Never commit `.env` files, passwords, API keys, database credentials, or JWT secrets to GitHub.

---

# Installation

## Prerequisites

Install the following before running the CRM locally:

- Node.js
- npm
- PostgreSQL
- Git

## 1. Clone the Repository

```bash
git clone <your-crm-repository-url>
```

## 2. Navigate to the Project

```bash
cd CRM
```

## 3. Install Backend Dependencies

```bash
cd backend
npm install
```

## 4. Configure Environment Variables

Create a `.env` file inside the backend directory.

Add the required database, authentication, email, and Twilio configuration.

## 5. Start the Backend

```bash
npm run dev
```

## 6. Install Frontend Dependencies

Open a new terminal:

```bash
cd frontend
npm install
```

## 7. Start the Frontend

```bash
npm run dev
```

The terminal will display the local URL for the frontend application.

---

# Error Handling

The API uses HTTP status codes to indicate the result of requests.

| Status Code | Description |
|---|---|
| 200 | Request completed successfully |
| 201 | Resource created successfully |
| 400 | Bad request |
| 401 | Unauthorized |
| 403 | Forbidden |
| 404 | Resource not found |
| 500 | Internal server error |

---

# Troubleshooting

## Backend Does Not Start

Check the following:

1. Make sure Node.js is installed.
2. Run `npm install`.
3. Check that the `.env` file exists.
4. Verify the environment variables.
5. Check whether the required port is available.

## Database Connection Error

Check:

1. PostgreSQL is running.
2. The database URL is correct.
3. Database credentials are valid.
4. The database exists.
5. Backend environment variables are configured correctly.

## Authentication Error

Check:

1. Login credentials are correct.
2. JWT secret is configured.
3. JWT token is being sent with protected requests.
4. The token is valid and has not expired.

## Email Notification Error

Check:

1. Email service credentials are correct.
2. SMTP configuration is correct.
3. Required email environment variables are configured.
4. The backend can connect to the email service.

## Twilio Error

Check:

1. Twilio account credentials are correct.
2. Twilio phone number configuration is correct.
3. Required Twilio environment variables are configured.
4. The requested communication service is enabled.

## File Upload Error

Check:

1. The file type is supported.
2. The file size is within the configured limit.
3. The upload endpoint is correct.
4. Multer configuration is correct.
5. The upload directory is available.

## Frontend Notification Error

If toast notifications are not displayed:

1. Check that React-Toastify is installed.
2. Verify that the toast container is configured.
3. Check the notification function calls.
4. Check browser console errors.

---

# Security

The CRM uses authentication and authorization mechanisms to protect application resources.

Security practices include:

- Store JWT secrets in environment variables.
- Do not commit `.env` files.
- Use HTTPS in production.
- Protect administrative and authenticated routes.
- Validate incoming API data.
- Secure database credentials.
- Keep third-party API credentials private.
- Avoid exposing sensitive information in API responses.
- Keep dependencies updated.

---

# Testing

The CRM APIs can be tested using Postman.

### Authentication Testing

- User registration
- User login
- Invalid credentials
- Protected routes
- Invalid JWT
- Expired JWT
- Unauthorized access

### CRM Module Testing

- Lead CRUD operations
- Company CRUD operations
- Deal management
- Ticket management

### Integration Testing

- File uploads
- Email notifications
- Twilio SMS
- OTP verification
- Frontend toast notifications

---

# Deployment

The CRM frontend and backend can be deployed as separate services.

### Deployment Checklist

1. Configure production environment variables.
2. Configure the production PostgreSQL database.
3. Configure the frontend API URL.
4. Configure backend CORS.
5. Configure JWT secrets securely.
6. Configure Nodemailer credentials.
7. Configure Twilio credentials.
8. Deploy the backend.
9. Deploy the frontend.
10. Test authentication.
11. Test CRM modules.
12. Verify email and Twilio integrations.

---

# Future Improvements

Possible future improvements include:

- Advanced CRM analytics
- Dashboard reports
- Advanced search and filtering
- Automated testing
- OpenAPI/Swagger API documentation
- Advanced role and permission management
- Activity tracking
- Improved notification management
- Automated email workflows
- Advanced deal pipeline analytics

---

# Documentation

The CRM documentation can include:

- README
- Installation Guide
- API Documentation
- Authentication Guide
- User Guide
- Admin Guide
- Troubleshooting Guide
- Integration Documentation

---

# Author

**Sooryajith**

## License

This project is intended for learning and portfolio purposes.
