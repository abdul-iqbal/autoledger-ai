# Tech Stack: AutoLedger

## Frontend

### Framework

* Next.js (App Router)
* React
* TypeScript

### UI Styling

* CSS Modules for dashboard screens
* Tailwind CSS for utility usage and global styling

### Design Approach

* Shared dashboard shell for navigation and top bar
* Page-level modular components
* Consistent user experience across all modules

### Core Screens

* Dashboard
* Inbox
* Workflows
* Vendors
* Reports
* Voice
* Settings

### Quality Baseline

* Responsive desktop layouts
* Tablet support
* Mobile support
* Accessibility-first controls
* Keyboard navigation support
* Focus-state compliance

---

## Backend

### Application Runtime

* Next.js API Routes
* Node.js Runtime

### Language

* TypeScript

### Architecture Pattern

#### Frontend Routes

```text
src/app/(app)/dashboard/**
```

#### API Routes

```text
src/app/api/**
```

#### Business Logic

```text
src/lib/**
```

---

### Core Domain Modules

* Dashboard Data & Actions
* Authentication & Session Management
* Policy & Autonomy Engine
* Inbox Lifecycle Management
* Approval Workflows
* Reporting Engine

---

### Background Workers

#### Extraction Worker

Responsible for:

* OCR Processing
* Invoice Extraction
* Receipt Processing
* Confidence Scoring

#### ERP Sync Worker

Responsible for:

* ERPNext Synchronization
* Journal Posting
* Vendor Updates

#### Reports Worker

Responsible for:

* KPI Generation
* Financial Reports
* Exception Reporting

#### Voice Worker

Responsible for:

* Speech-to-Text
* Voice Commands
* Voice Authentication

---

## Database

### Primary Database

* PostgreSQL

### ORM

* Prisma

### Schema Management

* Prisma Schema
* Prisma Migrations

### Data Characteristics

#### Multi-Company Support

Each company maintains:

* Independent policies
* Approval chains
* Workflow rules

#### Audit Persistence

All decisions and actions are stored for traceability.

#### Retention Policy

Default behavior:

* Retain data indefinitely
* Hard delete only upon explicit user request

---

## AI Components

### Policy & Autonomy Engine

Supports three operational modes:

#### Autonomous

System executes actions automatically except hard-stop events.

#### Semi-Autonomous

System executes actions based on configurable approval thresholds.

#### Manual

All actions require human approval.

---

### Hard-Stop Approval Engine

Mandatory approval events:

* New Vendor
* Duplicate Invoice Risk
* Missing Purchase Order
* Unknown Sender
* Tax Impacting Entry
* Payment Release
* Invoice Anomalies

---

### Document Intelligence Layer

Capabilities include:

* Invoice Intake
* OCR Processing
* PDF Parsing
* Data Extraction
* Confidence Scoring
* Coding Recommendations
* Exception Detection

---

### Communication Intelligence Layer

#### Email Workflows

* Email Reading
* Email Drafting
* Follow-Up Automation

#### Voice Workflows

* Inbound Calling
* Outbound Calling
* Voice-Based Approvals

#### Trust Verification

* PIN Verification
* Voice Recognition
* Approved Email Verification

---

### Action Layer

Responsible for:

* Approval Routing
* Journal Posting
* Workflow Triggers
* Task Scheduling
* Summary Generation
* Audit Logging

---

## ERP Integration Layer

### MVP Integrations

* ERPNext

### Planned Integrations

* QuickBooks
* Xero
* Sage
* Custom ERP Platforms

---

## Deployment Strategy

### Environment Model

Development Flow:

```text
Local Development
      ↓
    Staging
      ↓
  Production
```

---

### Platform Direction

#### Frontend

* Vercel Deployment

#### API Layer

* Next.js Server Runtime

#### Database

* Managed PostgreSQL

---

### Operational Strategy

Background workers deployed independently:

* Extraction Worker
* ERP Worker
* Reports Worker
* Voice Worker

Environment-variable driven integration management for:

* ERP Systems
* Email Providers
* Voice Providers
* AI Services

---

## Release Quality Controls

### Engineering Standards

* Type Checking
* Linting
* Targeted Testing
* Code Review

### Quality Assurance

* Dashboard Validation
* Workflow Validation
* ERP Integration Testing
* Approval Flow Testing
* Regression Testing

### Production Readiness

All releases must pass:

* Functional Testing
* Performance Validation
* Security Review
* User Acceptance Testing

---

## Technology Vision

AutoLedger is designed as a modern AI-native accounting platform built around policy-constrained autonomy, auditability, enterprise reliability, and scalable multi-company operations.

