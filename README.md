# TransitOps (v3.0.0) — Smart Transport Operations Platform

TransitOps is a production-ready, full-stack **Smart Transport Operations Platform** designed to streamline fleet deployment, vehicle compliance, dispatch operations, maintenance schedules, driver registries, and overall fleet logistics. 

Designed for scalability and operational clarity, TransitOps provides fleet managers and administrative operators with deep visibility and full control over their shipping, maintenance, and driver pipelines.

---

## 🏗️ Technical Architecture

TransitOps is engineered with a modular, high-performance full-stack structure:

- **Frontend (Client SPA)**:
  - **Framework**: React 18+ with Vite for ultra-fast, lightweight loading.
  - **Styles**: Custom-tailored, responsive **Tailwind CSS** focusing on elegant typography, precise component spacing, and zero margin clutter.
  - **Visual Elements**: Interactive charts and performance statistics with **Recharts**, and visual vector iconography via **Lucide React**.
  - **Transitions**: Smooth micro-animations powered by **Framer Motion** (`motion/react`) for seamless dashboard and modal flows.
  - **File Assets**: Supports fully client-safe base64 uploads for images, PDFs, and rich text documents.

- **Backend (Server)**:
  - **Engine**: Node.js & **Express** server configured as a single entry point (`server.ts`).
  - **Type Safety**: Fully typed with **TypeScript** utilizing native compilation mechanisms.
  - **Bundling**: Compiles utilizing an optimized production pipeline with `esbuild` to compile everything down to a single, standalone CJS file (`dist/server.cjs`), bypassing traditional relative import ESM errors in runtime containers.
  - **Local State & Persistence**: Resilient server-side repositories (`userRepo`, `driverRepo`, `vehicleRepo`, etc.) that mimic enterprise databases, backed by client-side browser synchronization.

---

## 🌟 Enhanced Core Features (v3)

### 🧑‍💼 Advanced Profile & Identity Management
An absolute central piece of compliance is verifying who operates your fleet. TransitOps features a comprehensive user-centric profile framework:
* **Dynamically Adaptive Forms**: Registration and edit screens adapt instantly based on whether the operator is a **Driver** or has an administrative/non-driver role (e.g., **Admin**, **Accountant**, **Mechanic**).
* **Multi-Repo Synchronization**: Editing an operator's profile dynamically updates both their primary User login state and their secondary operational Driver registry in real-time, preventing orphaned profile data.
* **Granular Background Metrics**: Collects and validates critical business data, including past employer history, descriptive expertise text summaries, years of city-specific driving, preferred vehicle category profiles, and territorial cities.

### 📎 Drag-and-Drop File Upload Engine
Say goodbye to text references for critical driver licenses. The platform features an active drag-and-drop uploader built from scratch:
* **Interactive Dropzone**: Responsive dragover, dragenter, and dragleave states with vivid color cues.
* **Instant Conversions**: Instantly compiles uploaded documents (PDF, PNG, JPEG, DOC, DOCX) into secure, highly-portable base64 strings server-bound.
* **Live Previews**: Dynamic preview panes for image uploads alongside persistent filename bindings and quick-action removal controls.

### 📊 Full-Spectrum Logistics Management
TransitOps serves as a complete fleet center:
* **Vehicles Grid**: Track registration numbers, active compliance statuses, current odometer readings, and payload thresholds.
* **Driver Deployment**: Manage current shifts, assigned routes, driver statuses (active, rest, off-duty), and contact info.
* **Trip & Fuel Audits**: Log routes from origin to destination, register fuel costs, track fuel efficiency per km, and audit trip expenses.
* **Maintenance & Expenses**: Monitor pending mechanical repairs, schedule preventive overhauls, and generate beautiful visual cost breakdowns.

---

## 🚀 Getting Started

Follow these steps to run and build TransitOps locally or deploy it to a staging environment:

### 1. Prerequisites
Ensure you have **Node.js** (v18 or higher) and **npm** installed.

### 2. Install Dependencies
Install all required libraries, packages, and tools:
```bash
npm install
```

### 3. Environment Setup
Configure your environment variables by copying `.env.example` to `.env`:
```bash
cp .env.example .env
```
Ensure the following variables are present (though AI Studio automates this at runtime):
* `GEMINI_API_KEY`: API key for generative logic.
* `APP_URL`: Self-referential URL for deployments.

### 4. Running the Development Server
Launches the full-stack system with TSX booting the Express entry point, which hosts both our backend REST API routes and proxy-serves our Vite assets in development:
```bash
npm run dev
```
The application will be accessible at: `http://localhost:3000`

### 5. Production Build & Bundling
Compile the React application and bundle the Express server into `dist/` with:
```bash
npm run build
```
This triggers:
1. `vite build` — Optimizes client-side code and outputs files to `dist/`.
2. `esbuild server.ts ...` — Bundles the Node backend into a robust CommonJS module at `dist/server.cjs`.

### 6. Starting Production Server
Run the optimized production build using:
```bash
npm start
```

---

## 🎨 Design Systems & Conventions
* **Aesthetic Intent**: Crafted under a clean, high-contrast, professional workspace theme using slate grays, sharp dark headers, emerald green accents, and generous layout spacing.
* **Typography Pairing**: Features `Inter` sans-serif as the high-readability UI base, paired with modern technical status flags highlighted in `JetBrains Mono` space patterns.
* **Desktop-First Polish**: Responsive breakpoints optimize standard high-density logistics desk setups while maintaining structural integrity for mobile devices.
