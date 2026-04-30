# Student Housing Hub

A housing marketplace for college students to discover, list, and connect around rental properties near their universities.

Built by Jack Snyder, Gabriel Puente, MacKay Roy, and Josh Gilbert — Utah Tech University CodeSchool.

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Vue.js 3 (CDN), HTML/CSS, Google Maps API |
| Backend | Node.js, Express.js |
| Database | MongoDB + Mongoose |
| File Storage | AWS S3 |
| Auth | express-session + bcryptjs |

---

## Features

- **Browse & Search** — Filter listings by rent range, bedrooms, bathrooms, WiFi, parking, washer/dryer, and more
- **Create Listings** — Upload photos, add amenities, set rent and property details
- **Google Maps Integration** — Address autocomplete and distance from college calculation
- **User Accounts** — Sign up, log in, edit profile, view your own listings
- **Image Uploads** — Photos stored in AWS S3

---

## Getting Started

### Prerequisites

- Node.js 20+
- MongoDB instance (Atlas or local)
- AWS S3 bucket

### Install

```bash
npm install
```

### Configure

Create a `.env` file in the project root:

```env
DB_LINK=mongodb+srv://<user>:<password>@<cluster>.mongodb.net/<database>
AWS_BUCKET_NAME=your-bucket-name
AWS_BUCKET_REGION=us-east-1
AWS_ACCESS_KEY=your-access-key
AWS_SECRET_KEY=your-secret-key
```

### Run

```bash
node server/index.js
```

Open [http://localhost:8080](http://localhost:8080) in your browser.

---

## Project Structure

```
├── server/
│   ├── index.js      # Express app and all API routes
│   ├── model.js      # Mongoose schemas (User, Property, Photo)
│   └── s3.js         # AWS S3 upload/download helpers
└── public/
    ├── index.html           # Home page
    ├── indexPage/           # Home page Vue app
    ├── createListing/       # Create listing Vue app
    ├── SearchSort/          # Search & filter Vue app
    └── PropertyView/        # Property detail Vue app
```

---

## API Overview

| Method | Route | Description |
|--------|-------|-------------|
| POST | `/session` | Login |
| DELETE | `/session` | Logout |
| POST | `/users` | Register |
| GET/PUT | `/users/:id` | Get / update user |
| GET/POST | `/properties` | List all / create property |
| GET/PUT/DELETE | `/properties/:id` | Get / update / delete property |
| POST | `/images` | Upload image to S3 |
| GET | `/images/:bucket/:key` | Retrieve image from S3 |
