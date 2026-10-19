# XenZ Technologies

**Learn AI skills. Discover useful tools. Build career-ready experience.**

XenZ Technologies is an AI learning and productivity website for students and professionals. It combines a dark, responsive landing page with AI-tool discovery, enrollment, online payment processing, certificate pages, and an admin dashboard for enrollment reporting.

<p align="left">
  <a href="https://xenztechnologies.in/"><strong>🌐 Visit the Live Website</strong></a>
  &nbsp; · &nbsp;
  <a href="https://github.com/maahii-in/Xenz-Technologies"><strong>View Source Code</strong></a>
</p>

---

## ✨ Highlights

- **AI Learning:** A landing page introducing live AI classes and practical, career-oriented learning.
- **AI Productivity Tools:** A dedicated page for discovering useful AI tools.
- **Enrollment System:** A form for collecting learners' names, mobile numbers, and email addresses.
- **Razorpay Integration:** Supports payment order creation and payment signature verification.
- **Training Access:** Returns the configured training or meeting link after successful payment verification.
- **Enrollment Records:** Supports saving enrollment details to Google Sheets when credentials are configured.
- **WhatsApp Notifications:** Supports optional WhatsApp Cloud API enrollment confirmation messages.
- **Admin Dashboard:** Displays enrollment and revenue summaries, a seven-day enrollment chart, a searchable student table, and CSV export.
- **Certificate Pages:** Includes certificate and supporting pages for the enrollment experience.
- **Responsive UI:** Features a dark navy background, cyan accents, modern cards, and an animated snowfall effect.

> Note: Promotional figures displayed on the website are editable website content and should not be interpreted as independently verified business statistics.

---

## 🌐 Live Website

**Website:** https://xenztechnologies.in/

**GitHub Repository:** https://github.com/maahii-in/Xenz-Technologies

Visit the live website to explore the homepage, AI tools, enrollment experience, and other available features.

---

## 🖥️ Screenshots

The website features a modern, dark-themed interface designed to provide a clean experience for students and professionals.

### Homepage
- Dark navy background with animated particles.
- XenZ Technologies branding.
- Main call-to-action for enrollment.
- Statistics and feature cards.
- Responsive navigation.

### AI Tools
- Dedicated AI tools page.
- Productivity-focused learning resources.
- A user-friendly interface for discovering useful tools.

### Enrollment and Administration
- Enrollment form and Razorpay checkout integration.
- Payment confirmation and success pages.
- Admin dashboard for viewing enrollment information.

---

## 🧰 Technology Stack

| Technology | Purpose |
|---|---|
| HTML5 | Website structure |
| CSS3 | Layout, styling, animations, and responsive design |
| JavaScript | Frontend interactions and API integration |
| Node.js | Backend runtime |
| Express.js | Backend API and static file serving |
| Razorpay | Online payment processing |
| Google Sheets API | Optional enrollment data storage |
| WhatsApp Cloud API | Optional enrollment confirmation messages |
| dotenv | Environment variable configuration |
| CORS | Cross-origin request configuration |
| Google Fonts | Typography using Poppins |

---

## 📂 Project Structure

```text
Xenz-Technologies/
├── frontend/                # Additional frontend files
├── yaml/                    # YAML configuration files
├── .env.example             # Environment variable template
├── .gitignore               # Git ignore rules
├── CNAME                    # Custom domain configuration
├── _config.yml              # Site configuration
├── admin.html               # Admin dashboard
├── ai-tools.html            # AI productivity tools
├── certificate.html         # Certificate page
├── content.html             # Content/contact page
├── enroll.html              # Enrollment and payment page
├── exclude.html             # Supporting page
├── index.html               # Homepage
├── payment-confirm.html     # Payment confirmation page
├── receipt.html             # Receipt page
├── success.html             # Enrollment success page
├── server.js                # Node.js and Express backend
├── server.txt               # Supporting server file
├── package.json             # Dependencies and npm scripts
├── package-lock.json        # Locked dependency versions
├── students.json            # Student-related JSON data
├── logo.png                 # Logo asset
├── phone.png                # Image asset
├── simplecetifi.png         # Certificate image
├── simplecetifi.png         # Certificate-related image asset
└── xzt.png                  # XenZ Technologies logo
```

The repository may contain additional assets and supporting files.

---

## 🚀 Getting Started

Follow these steps to run the project on your local machine.

### Prerequisites

Install the following before starting:

- [Node.js](https://nodejs.org/) version 18 or later.
- npm, which is included with Node.js.
- Git.
- Razorpay credentials if you want to test the payment flow.
- Google Sheets and WhatsApp credentials if you want to enable those optional integrations.

### 1. Clone the Repository

```bash
git clone https://github.com/maahii-in/Xenz-Technologies.git
```

Navigate to the project directory:

```bash
cd Xenz-Technologies
```

### 2. Install Dependencies

Run the following command:

```bash
npm install
```

### 3. Configure Environment Variables

Create a `.env` file from the example configuration.

On macOS/Linux:

```bash
cp .env.example .env
```

On Windows Command Prompt:

```cmd
copy .env.example .env
```

Open the `.env` file and configure the required values.

See the Configuration section below for details.

### 4. Configure the Frontend API URL

The enrollment page and admin dashboard use an `API_BASE` constant to connect to the backend.

For local development, update the relevant value in `enroll.html` and `admin.html`:

```javascript
const API_BASE = 'http://localhost:5000';
```

Use the existing deployed backend URL when testing against the hosted backend instead.

**Important:** Never place private API keys, payment secrets, or administrator credentials in frontend JavaScript.

### 5. Start the Application

Start the server:

```bash
npm start
```

For development with automatic server restarts:

```bash
npm run dev
```

Open the website in your browser:

```text
http://localhost:5000
```

Check the backend health endpoint:

```text
http://localhost:5000/api/health
```

> Payment processing requires valid Razorpay configuration. Without Google Sheets credentials, the enrollment storage fallback is temporary and may be lost when the server restarts.

---

## ⚙️ Configuration

Configure these environment variables in your `.env` file or deployment environment.

| Variable | Description |
|---|---|
| `PORT` | Port used by the Express server. Defaults to `5000`. |
| `ADMIN_PASSWORD` | Password used to access protected admin functionality. |
| `MEET_LINK` | Training or meeting URL returned after successful enrollment. |
| `RAZORPAY_KEY_ID` | Razorpay public key ID. |
| `RAZORPAY_KEY_SECRET` | Secret used for payment signature verification. |
| `ENROLLMENT_PRICE` | Enrollment price in paise. For example, `3700` means ₹37. |
| `GOOGLE_SERVICE_ACCOUNT_EMAIL` | Google Cloud service account email. |
| `GOOGLE_PRIVATE_KEY` | Private key associated with the Google service account. |
| `GOOGLE_SHEET_ID` | ID of the Google spreadsheet used for enrollment records. |
| `WHATSAPP_PHONE_NUMBER_ID` | WhatsApp Cloud API phone-number ID. |
| `WHATSAPP_ACCESS_TOKEN` | WhatsApp Cloud API access token. |
| `WHATSAPP_TEMPLATE_NAME` | Approved WhatsApp message template name. |

### Razorpay Configuration

1. Create or sign in to your Razorpay account.
2. Obtain your API credentials from the Razorpay dashboard.
3. Add the key ID and key secret to your environment variables.
4. Use test credentials while developing.
5. Verify payment handling before switching to live credentials.

Keep the Razorpay key secret on the backend only.

### Google Sheets Integration

To store enrollment records in Google Sheets:

1. Create a project in Google Cloud.
2. Enable the Google Sheets API.
3. Create a service account.
4. Share the spreadsheet with the service account email and grant Editor access.
5. Configure the service account email, private key, and spreadsheet ID in `.env`.

The current backend uses a sheet tab named `Sheet1` and stores enrollment-related information in columns A:G.

Check the implementation in `server.js` before changing your spreadsheet structure.

### WhatsApp Integration

To enable enrollment confirmation messages:

1. Configure your WhatsApp Business Cloud API.
2. Obtain the phone-number ID and access token.
3. Create and approve the required message template.
4. Add the credentials and template name to `.env`.
5. Test message delivery before using it in production.

Never publish your WhatsApp access token in the repository.

---

## 🔌 API Reference

The backend API is implemented in `server.js`.

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/health` | Checks the backend status. |
| `GET` | `/api/razorpay-key` | Returns the configured Razorpay public key. |
| `POST` | `/api/create-order` | Creates a Razorpay payment order. |
| `POST` | `/api/verify-payment` | Verifies payment details and processes enrollment. |
| `POST` | `/api/admin/login` | Checks administrator login credentials. |
| `GET` | `/api/students` | Retrieves enrollment records for the admin dashboard. |
| `GET` | `/api/analytics` | Retrieves enrollment and revenue summaries. |
| `GET` | `/api/export` | Exports enrollment records as CSV. |

Protected admin endpoints require administrator authentication as implemented in the backend.

For sensitive production applications, prefer secure session-based authentication and avoid transmitting credentials in URL query parameters.

---

## 📊 Admin Dashboard

The admin dashboard provides functionality for managing enrollment information.

Features include:

- Administrator login.
- Student enrollment records.
- Enrollment and revenue summaries.
- Seven-day enrollment analytics.
- Student search.
- CSV export.

Configure a strong, unique administrator password before deploying the application.

---

## 💳 Payment Flow

The enrollment payment process follows this general sequence:

1. The learner submits the enrollment form.
2. The frontend requests a payment order from the backend.
3. The learner completes the payment through Razorpay Checkout.
4. The frontend submits payment details for verification.
5. The backend verifies the Razorpay payment signature.
6. After successful verification, enrollment processing is performed.
7. Enrollment information can be stored in Google Sheets.
8. An optional WhatsApp confirmation can be sent.
9. The learner receives the configured training or meeting link.

Always rely on server-side payment verification rather than trusting a frontend success message.

---

## 🌍 Deployment

The project contains static HTML pages and an Express backend. You can deploy them together or separately.

### Backend Deployment

The Node.js backend can be deployed to a Node.js hosting provider, such as [Render](https://render.com/).

General steps:

1. Connect your GitHub repository to the hosting provider.
2. Configure the build command:

   ```bash
   npm install
   ```

3. Configure the start command:

   ```bash
   npm start
   ```

4. Add the required environment variables in the provider's dashboard.
5. Deploy the application.
6. Verify the health endpoint.
7. Update the frontend API URL to point to the deployed backend.

The exact deployment options depend on your hosting provider.

### Frontend Deployment

The static HTML pages can be served by the Express application or hosted on a static-site platform.

If the frontend and backend use different domains:

- Set the correct backend URL in `enroll.html` and `admin.html`.
- Configure the backend CORS allow-list for the production frontend origin.
- Use HTTPS for both frontend and backend.
- Test enrollment and payment verification.
- Confirm that administrator authentication works.
- Test optional integrations separately.

---

## 🔐 Security Best Practices

Follow these recommendations before using the project in production:

- Never commit `.env` files or private credentials.
- Use a strong administrator password.
- Keep Razorpay secrets on the backend.
- Protect Google service-account keys and WhatsApp access tokens.
- Test payment operations with Razorpay test credentials first.
- Review administrator authentication and session handling.
- Avoid sending passwords in URL query parameters.
- Configure production CORS rules carefully.
- Use HTTPS in production.
- Use a persistent database or properly configured storage instead of relying on temporary in-memory enrollment data.
- Validate and sanitize user input on the backend.
- Review error handling and logging to ensure sensitive information is not exposed.

---

## 🛠️ Available Commands

| Command | Description |
|---|---|
| `npm install` | Installs project dependencies. |
| `npm start` | Starts the Express server. |
| `npm run dev` | Starts the server in development mode using Nodemon. |

---

## 🤝 Contributing

Contributions, suggestions, and bug reports are welcome.

To contribute:

1. Fork the repository.
2. Create a feature branch.

   ```bash
   git checkout -b feature/your-feature
   ```

3. Make your changes and test them.
4. Commit your changes.

   ```bash
   git add .
   git commit -m "Add your feature"
   ```

5. Push the branch.

   ```bash
   git push origin feature/your-feature
   ```

6. Open a pull request describing your changes.

For larger changes, consider opening an issue before starting implementation.

---

## 📄 License

No license file is currently included in the repository.

Add a `LICENSE` file to specify the terms under which others may use, modify, and distribute this project.

Until a license is added, do not assume the project is available for unrestricted reuse.

---

## 👨‍💻 Project

**XenZ Technologies**

Website: https://xenztechnologies.in/

Repository: https://github.com/maahii-in/Xenz-Technologies

---

Made with 💙 by **XenZ Technologies**
