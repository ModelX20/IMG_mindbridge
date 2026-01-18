# MindBridge 🌿

<div align="center">
  <h3>Bridges for the Mind, Circles of Support</h3>
  <p>A safe sanctuary for your mental wellbeing. Connect with supportive circles, track your journey, and find your calm in the chaos.</p>
</div>

---

## 🌟 Features

*   **🛡️ Auth & Security**: Secure user registration and login functionality.
*   **🫂 Circles of Support**: Join or create 'Circles' to connect with like-minded individuals.
*   **✍️ Journaling**: A private space to log your thoughts and reflections.
*   **📊 Mood Tracking**: Monitor your emotional well-being over time with visual analytics.
*   **💬 Community Posts**: Share thoughts and interact within your circles.
*   **🎨 Modern UI**: A calming, responsive interface built with the latest web technologies.

## 🛠️ Tech Stack

*   **Framework**: Next.js 15 (App Directory)
*   **Database**: SQLite (via Prisma)
*   **ORM**: Prisma
*   **Authentication**: Custom JWT-based Auth
*   **Styling**: Tailwind CSS & Lucide Icons
*   **Language**: TypeScript

---

## 🚀 Getting Started

Follow these steps to set up the project locally on your machine.

### Prerequisites

Ensure you have the following installed:
*   [Node.js](https://nodejs.org/) (v18 or higher recommended)
*   [npm](https://www.npmjs.com/) (usually comes with Node.js)
*   [Git](https://git-scm.com/)

### 1. Clone the Repository

```bash
git clone https://github.com/ModelX20/IMG_mindbridge.git
cd IMG_mindbridge
```

*(Note: If you are using the local folder directly, just navigate to the project root)*

### 2. Install Dependencies

Install the required packages using npm:

```bash
npm install
```

### 3. Environment Setup

The application needs to know *where* your database is located. We use a `.env` file for this configuration.

1.  Create a file named `.env` in the root folder of the project.
2.  Add the following lines:

```bash
# file: .env

# This tells Prisma to use a local SQLite file named 'dev.db' located in the 'prisma' folder
DATABASE_URL="file:./dev.db"

# This secret key is used to sign and verify user login tokens (JWTs).
# You can use any random string here (e.g., "my-secret-password-123")
JWT_SECRET="your-secure-random-secret-key"
```

### 4. Database Setup

Now we need to create the actual database file and set up the tables (Users, Circles, Posts, etc.).

Run the following commands in your terminal:

```bash
# 1. Generate the Prisma Client
#    (This creates the custom TypeScript code used to talk to your database)
npx prisma generate

# 2. Push Schema to Database
#    (This looks at 'prisma/schema.prisma' and creates the 'dev.db' file
#     with all the correct tables and columns)
npx prisma db push
```

*Success verify:* You should see a message saying "🚀  Your database is now in sync with your Prisma schema."

### 5. Run the Application

Start the development server:

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

---

## 📂 Project Structure

```
├── prisma/            # Database schema and SQLite file
├── public/            # Static assets (images, uploads)
├── src/
│   ├── app/           # Next.js App Router pages & API routes
│   ├── components/    # Reusable UI components
│   ├── lib/           # Utility functions (db, auth, etc.)
│   └── ...
├── .env               # Environment variables (do not commit secrets!)
└── package.json       # Project dependencies and scripts
```

