# .githingore
Food and groceries delivery app
# dependencies
node_modules
.pnp
.pnp.js

# testing
coverage

# next.js / build outputs
.next/
out/
build
dist
.turbo

# misc
.DS_Store
*.pem

# debug
npm-debug.log*
yarn-debug.log*
yarn-error.log*
pnpm-debug.log*

# env files (NEVER PUSH THESE)
.env
.env*.local
.env.development.local
.env.test.local
.env.production.local

# expo / react native
.expo/
*.jks
*.p8
*.mobileprovision
*.orig.*

# vercel
.vercel
# MK Design E-Commerce & Delivery Platform

A full-stack, modular e-commerce platform and real-time delivery tracking system built for MK Design. The platform features an organic, nature-inspired design system tailored for showcasing craft products, key charms, gifts, hampers, jewelry, and accessories, complete with an integrated WhatsApp ordering flow.

## 🏗 Architecture

This project is structured as a monorepo using **Turborepo** and **pnpm**, divided into three core applications and shared packages:

- **Client App (`apps/client-app`):** A Next.js frontend providing a seamless shopping experience and real-time map tracking for customers.
- **Admin Panel (`apps/admin-panel`):** A Next.js dashboard for managing orders, inventory, and dispatching.
- **Driver App (`apps/driver-app`):** An Expo (React Native) mobile application featuring offline-first capabilities, background GPS tracking, and digital proof of delivery.
- **Backend API (`apps/backend-api`):** A NestJS service handling business logic, PostgreSQL database connections (via Prisma), and a Socket.io / Redis gateway for live tracking.

## 🚀 Tech Stack

- **Frontend:** Next.js (App Router), React, Tailwind CSS, Framer Motion, Zustand
- **Mobile:** React Native, Expo, Mapbox GL
- **Backend:** Node.js, NestJS, Socket.io
- **Database & Queue:** PostgreSQL, Prisma ORM, Redis, BullMQ
- **Integrations:** Meta WhatsApp Business API, AWS S3 / Cloudflare R2 (for image storage)

## 🛠 Local Development Setup

### Prerequisites
- Node.js (v18+)
- pnpm (v8+)
- Docker (for local databases)
- Expo CLI

### 1. Installation
Clone the repository and install the dependencies:
\`\`\`bash
git clone https://github.com/YOUR_USERNAME/mk-design-platform.git
cd mk-design-platform
pnpm install
\`\`\`

### 2. Environment Variables
Copy the example environment files and fill in your credentials:
\`\`\`bash
cp .env.example .env
\`\`\`
*(Ensure you add your WhatsApp API token and PostgreSQL connection strings).*

### 3. Start the Databases
Spin up the local PostgreSQL and Redis instances using Docker:
\`\`\`bash
pnpm run db:up
\`\`\`

### 4. Database Migrations
Push the Prisma schema to your local database and generate the client:
\`\`\`bash
pnpm --filter @delivery/database run push
pnpm --filter @delivery/database run generate
\`\`\`

### 5. Run the Workspace
Start all applications concurrently via Turborepo:
\`\`\`bash
pnpm run dev
\`\`\`
- Client App runs on `http://localhost:3000`
- Admin Panel runs on `http://localhost:3001`
- NestJS API runs on `http://localhost:3002`

## 💬 WhatsApp Integration

The platform utilizes the WhatsApp Business API to dispatch automated digital proof of delivery, tracking links, and order confirmations directly to customers. The primary support and ordering contact route is configured for **+91-7015688124**.

## ✉️ Support & Contact

For technical inquiries or system support, please reach out to **mk.dkdesign@gmail.com**.
