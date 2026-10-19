# XenZ Technologies

### AI Learning · Smart Tools · Career Development

XenZ Technologies is a web-based learning platform designed to help students and professionals explore AI tools, improve productivity, and develop practical digital skills.

The platform combines a modern, responsive website with an enrollment workflow, online payment integration, student record management, and administrative reporting.

<p align="left">
  <a href="https://xenztechnologies.in/">
    <img src="https://img.shields.io/badge/Live%20Website-Visit%20Now-0EA5E9?style=for-the-badge" alt="Visit Live Website">
  </a>
  <a href="https://github.com/maahii-in/Xenz-Technologies">
    <img src="https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github" alt="GitHub Repository">
  </a>
</p>

---

## Overview

XenZ Technologies provides a centralized web experience for discovering AI learning opportunities, accessing productivity resources, and enrolling in training programs.

The application includes a frontend built with HTML, CSS, and JavaScript, supported by a Node.js and Express backend. The backend handles enrollment requests, payment verification, student records, and administrative API operations.

### Key Features

- **AI Learning:** A dedicated landing page presenting AI classes and career-oriented learning opportunities.
- **AI Productivity Tools:** A dedicated page for exploring useful AI tools and resources.
- **Online Enrollment:** A form-based enrollment workflow for collecting student information.
- **Payment Integration:** Razorpay order creation and payment signature verification.
- **Student Management:** Enrollment record storage through Google Sheets when configured.
- **Admin Dashboard:** Enrollment records, revenue summaries, enrollment analytics, and CSV export.
- **Payment Confirmation:** Dedicated pages for payment confirmation, receipts, and enrollment success.
- **Certificate Support:** A dedicated certificate page.
- **WhatsApp Notifications:** Optional enrollment confirmation through the WhatsApp Cloud API.
- **Responsive Interface:** A modern dark-themed design with cyan accents, feature cards, and animated background elements.

---

## Live Project

| Resource | Link |
|---|---|
| Live Website | https://xenztechnologies.in/ |
| GitHub Repository | https://github.com/maahii-in/Xenz-Technologies |
| Main Page | `index.html` |
| AI Tools | `ai-tools.html` |
| Enrollment | `enroll.html` |
| Admin Dashboard | `admin.html` |
| Backend Server | `server.js` |

---

## Technology Stack

| Technology | Purpose |
|---|---|
| HTML5 | Website structure |
| CSS3 | Styling, layouts, animations, and responsive design |
| JavaScript | Frontend interactions and API integration |
| Node.js | Backend runtime |
| Express.js | HTTP server and REST API |
| Razorpay | Online payment processing |
| Google Sheets API | Optional enrollment data storage |
| WhatsApp Cloud API | Optional enrollment notifications |
| dotenv | Environment variable management |
| CORS | Cross-origin request configuration |
| Nodemon | Development server restarts |

---

## Project Structure

```text
Xenz-Technologies/
│
├── frontend/                # Frontend resources
├── yaml/                    # YAML configuration files
│
├── index.html               # Main landing page
├── ai-tools.html            # AI productivity tools page
├── enroll.html              # Enrollment and payment workflow
├── admin.html               # Admin dashboard
├── certificate.html         # Certificate page
├── content.html             # Supporting content page
├── payment-confirm.html     # Payment confirmation page
├── receipt.html             # Receipt page
├── success.html             # Enrollment success page
├── exclude.html             # Supporting page
│
├── server.js                # Express backend and API routes
├── server.txt               # Supporting server file
├── students.json            # Student-related JSON data
│
├── logo.png                 # Logo asset
├── phone.png                # Image asset
├── simple cetifi.png        # Certificate image asset
├── simplecetifi.png         # Certificate image asset
├── xzt.png                  # Brand image asset
│
├── .env.example             # Environment variable template
├── .gitignore               # Git ignore rules
├── .config.yml               # Not applicable; see _config.yml below
├── _config.yml              # Site configuration
├── CNAME                    # Custom domain configuration
├── package.json             # Dependencies and npm scripts
└── package-lock.json        # Dependency lock file
```

---

## Getting Started

Follow these steps to run the project locally.

### Prerequisites

Install the following:

- [Node.js](https://nodejs.org/) version 18 or later
- npm
- [Git](https://git-scm.com/)

Third-party credentials are required to test the corresponding payment and notification integrations.

### 1. Clone the Repository

```bash
git clone https://github.com/maahii-in/Xenz-Technologies.git
```

Navigate to the project directory:

```bash
cd Xenz-Technologies
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment Variables

Create a local `.env` file using the provided example.

**Windows Command Prompt**

```cmd
copy .env.example .env
```

**macOS / Linux**

```bash
cp .env.example .env
```

Open `.env` and update the configuration values using your own credentials.

See [Environment Configuration](#environment-configuration) for details.

### 4. Start the Application

Start the server:

```bash
npm start
```

For development:

```bash
npm run dev
```

The default local address is:

```text
http://localhost:5000
```

The backend health endpoint is available at:

```text
http://localhost:5000/api/health
```

The Express server serves the website files and API routes from the project directory.

---

## Environment Configuration

The application reads configuration values from environment variables using `dotenv`.

| Variable | Description |
|---|---|
| `PORT` | Server port. Defaults to `5000`. |
| `ADMIN_PASSWORD` | Password used by the current admin authentication implementation. |
| `MEET_LINK` | Meeting or training URL returned after successful payment verification. |
| `RAZORPAY_KEY_ID` | Razorpay public key identifier. |
| `RAZORPAY_KEY_SECRET` | Private Razorpay secret used for signature verification. |
| `ENROLLMENT_PRICE` | Enrollment amount in paise. For example, `3700` represents ₹37. |
| `GOOGLE_SERVICE_ACCOUNT_EMAIL` | Google Cloud service account email. |
| `GOOGLE_PRIVATE_KEY` | Private key for the Google service account. |
| `GOOGLE_SHEET_ID` | Google spreadsheet identifier. |
| `WHATSAPP_PHONE_NUMBER_ID` | WhatsApp Cloud API phone-number ID. |
| `WHATSAPP_ACCESS_TOKEN` | WhatsApp Cloud API access token. |
| `WHATSAPP_TEMPLATE_NAME` | Optional WhatsApp message template name. |

### Configuration Notes

- Use real credentials only in your local `.env` file or hosting provider's secure environment settings.
- Keep `RAZORPAY_KEY_SECRET`, `GOOGLE_PRIVATE_KEY`, and `WHATSAPP_ACCESS_TOKEN` private.
- For Google Sheets integration, enable the Sheets API and grant the service account access to the target spreadsheet.
- The WhatsApp variables are optional and should be configured only when the integration is needed.
- The Google Sheets integration expects a worksheet named `Sheet1` with the appropriate header row.
- Enrollment amounts are configured in paise, not rupees.

---

## Application Architecture

The application follows a straightforward client-server architecture.

```text
                 ┌─────────────────────────┐
                 │       Web Browser       │
                 │                         │
                 │ HTML · CSS · JavaScript │
                 └────────────┬────────────┘
                              │
                              │ HTTP Requests
                              ▼
                 ┌─────────────────────────┐
                 │      Express Server     │
                 │                         │
                 │ Static Files & REST API │
                 └────────────┬────────────┘
                              │
             ┌────────────────┼────────────────┐
             │                │                │
             ▼                ▼                ▼
      ┌────────────┐   ┌──────────────┐  ┌─────────────┐
      │  Razorpay  │   │ Google Sheets│  │  WhatsApp   │
      │  Payments  │   │   API        │  │ Cloud API   │
      └────────────┘   └──────────────┘  └─────────────┘
```

Google Sheets and WhatsApp integrations depend on the appropriate credentials and configuration. Razorpay payment functionality also requires valid API credentials.

---

## API Reference

The backend API is implemented in `server.js`.

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/health` | Returns backend and integration status. |
| `GET` | `/api/razorpay-key` | Returns the configured Razorpay public key. |
| `POST` | `/api/create-order` | Creates a Razorpay payment order. |
| `POST` | `/api/verify-payment` | Verifies the payment signature and processes enrollment. |
| `POST` | `/api/admin/login` | Validates administrator credentials. |
| `GET` | `/api/students` | Retrieves enrollment records. |
| `GET` | `/api/analytics` | Returns enrollment and revenue analytics. |
| `GET` | `/api/export` | Exports enrollment data as CSV. |

The student, analytics, and export endpoints use the current backend's administrator password check.

### Health Check Example

Request:

```http
GET /api/health
```

Example response:

```json
{
  "status": "ok",
  "sheetsConnected": false,
  "razorpayConfigured": true,
  "whatsappConfigured": false
}
```

The values in this example are illustrative. The actual response reflects the current server configuration.

---

## Enrollment and Payment Workflow

The enrollment workflow is designed around the following steps:

1. The student enters the required enrollment information.
2. The frontend requests a payment order from the backend.
3. The backend creates an order through Razorpay.
4. The student completes the payment through the payment interface.
5. Payment details are submitted to the backend for signature verification.
6. After successful verification, the backend processes the enrollment record.
7. The record is stored in Google Sheets when the integration is configured.
8. An optional WhatsApp confirmation is attempted.
9. The configured meeting or training URL is returned to the frontend.

Payment-related operations should always be validated on the server. A frontend success message alone is not proof of a successful payment.

---

## Student Data and Storage

The application supports Google Sheets for storing enrollment information.

The current implementation records fields including:

- Student name
- Mobile number
- Email address
- Enrollment amount
- Razorpay payment ID
- Razorpay order ID
- Enrollment timestamp

### Storage Behavior

When Google Sheets is configured and available, the server uses it to read and append enrollment records.

Otherwise, the current implementation falls back to an in-memory array. This fallback is temporary: its contents are lost when the Node.js process restarts.

For persistent records, configure Google Sheets correctly or replace the fallback with a persistent database.

---

## Admin Dashboard

The admin functionality provides access to enrollment and reporting operations.

Current backend capabilities include:

- Administrator password verification
- Student record retrieval
- Total enrollment calculation
- Revenue calculation from enrollment records
- Seven-day enrollment summaries
- Recent enrollment data
- CSV export

Before exposing the dashboard publicly, review the administrator authentication implementation and apply appropriate production security controls.

---

## Deployment

The project can be deployed to a Node.js hosting platform or adapted to a separate static frontend and backend deployment.

### Backend Deployment

1. Connect the GitHub repository to your hosting provider.
2. Install the project dependencies.
3. Set the start command to:

   ```bash
   npm start
   ```

4. Configure the environment variables in the hosting dashboard.
5. Deploy the application.
6. Test `/api/health`.
7. Verify the enrollment, payment, and admin workflows.

### Frontend Configuration

If the frontend and backend are deployed on different domains, update the API base URL used by the frontend pages.

The backend's CORS configuration must also allow the intended frontend origin.

Use HTTPS for production traffic and test the full payment flow before enabling live transactions.

---

## Security Considerations

The following practices are recommended before production use:

- Never commit `.env` files or private credentials.
- Use strong, unique administrator credentials.
- Keep payment verification and secrets on the backend.
- Validate enrollment inputs on the server.
- Restrict CORS to the required production origins.
- Use HTTPS for all production endpoints.
- Add rate limiting and stronger session-based administrator authentication as appropriate.
- Avoid transmitting passwords in query strings.
- Use persistent storage for important enrollment and payment records.
- Review error handling and logs to avoid exposing sensitive information.
- Test payment integration using Razorpay test credentials before switching to live mode.

---

## Development Commands

| Command | Purpose |
|---|---|
| `npm install` | Install dependencies. |
| `npm start` | Start the application server. |
| `npm run dev` | Run the server with Nodemon during development. |

---

## Contributing

Contributions, suggestions, and bug reports are welcome.

To contribute:

1. Fork the repository.
2. Create a feature branch.

   ```bash
   git checkout -b feature/your-feature
   ```

3. Implement and test your changes.
4. Commit your work.

   ```bash
   git add .
   git commit -m "Describe your changes"
   ```

5. Push the branch.

   ```bash
   git push origin feature/your-feature
   ```

6. Open a pull request with a clear description of the changes.

---

## License

A license file is not currently present in the repository. Add a `LICENSE` file to clearly establish the permissions and conditions for using, modifying, and distributing the project.

Until a license is specified, do not assume that unrestricted reuse is permitted.

---

## Contact & Links

**XenZ Technologies**

- Website: https://xenztechnologies.in/
- Repository: https://github.com/maahii-in/Xenz-Technologies

---

<p align="center">
  <strong>XenZ Technologies</strong><br>
  AI Learning · Productivity · Digital Skills
</p>
