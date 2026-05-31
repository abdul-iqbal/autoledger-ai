# AutoLedger MVP v1

## Problem Statement

Small business owners and lean accounting teams spend too much time on repetitive accounts payable and finance operations: collecting invoices, verifying details, coding transactions, chasing approvals, posting entries, and communicating with vendors or internal stakeholders.

Existing workflows are fragmented across email, spreadsheets, calls, and ERP systems, creating delays, errors, and poor auditability.

AutoLedger MVP v1 solves this by delivering an AI Accounting Operator that can read incoming documents and messages, reason over company policies, request required approvals, and execute approved actions in ERPNext while maintaining a complete audit trail.

---

## Target Users

### Primary Users

* Small business owners
* Founders
* Entrepreneurs

### Secondary Users

* Small accounting teams (1–3 people)

### Operational Context

* Multi-company ownership supported
* Policies and approvals configured per company

---

## Features

### 1. AI Operation Modes

#### Autonomous

Executes tasks automatically except hard-stop approval events.

#### Semi-Autonomous

Executes tasks based on configurable approval thresholds and rules.

#### Manual

Human-led operations with no autonomous execution.

---

### 2. Invoice Intake & Processing

* Ingest invoices from email and supported document inputs
* Extract key fields and confidence signals
* Apply coding suggestions and policy checks

#### Anomaly Detection Rules (MVP)

Flag invoices when:

* Invoice value exceeds 200% of vendor history
* Invoice amount exceeds expected vendor pattern by $5,000+

---

### 3. Approval & Safety Controls

#### Hard-Stop Approval Events

Always require internal approval:

* New Vendor
* Invoice Anomaly
* Missing Purchase Order
* Duplicate Invoice Risk
* Unknown Sender
* Tax-Impacting Entry
* Payment Release

---

### 4. Communication Layer

#### Email

* Draft and send emails within policy boundaries

#### Voice

* Inbound and outbound calling support

#### Identity Controls

Voice Approvals:

* PIN Verification
* Voice Recognition

Email Approvals:

* Approved Sender Verification

#### Restricted Actions

The following require internal approval:

* Bank Detail Changes
* Vendor Master Updates
* Sensitive Financial Instructions

---

### 5. Action Layer

* Create Accounting Entries
* Post Journals
* Trigger Workflows
* Schedule Follow-Ups
* Maintain Complete Audit Logs

---

### 6. Inbox Lifecycle

Required Statuses:

1. New
2. Needs Review
3. Awaiting Approval
4. Approved
5. Posted
6. Blocked
7. Closed

---

### 7. Reporting (MVP)

* AP Aging
* Cash Forecast
* Invoice Cycle Time
* Exception Log
* Vendor Risk Report

---

## User Journey

1. Invoice arrives via email.
2. AutoLedger extracts document data and confidence signals.
3. AutoLedger applies coding and policy checks.
4. If a hard-stop or policy trigger occurs, approval is requested.
5. Internal approver reviews and approves/rejects.
6. On approval, AutoLedger posts to ERPNext.
7. AutoLedger sends a summary and records a complete audit trail.

---

## MVP Scope

### In Scope

* ERPNext as accounting source of truth
* Mode-based execution engine
* Hard-stop policy enforcement
* Invoice intake and extraction
* Approval routing
* ERP posting
* Summary notifications
* Email and voice communication
* Per-company policy configuration
* Core reporting package
* Data retention and deletion controls

### Out of Scope (Post-MVP)

* Marketplace integrations
* Advanced forecasting
* Custom BI builders
* Open-ended AI command execution
* Global tax automation

---

## Success Metrics

### Product Outcomes

* End-to-End Automation Rate
* Cycle Time Reduction
* Approval Efficiency
* Exception Precision

### Operational Outcomes

* Posting Accuracy
* Duplicate Prevention Rate
* Policy Compliance Rate
* Audit Completeness

### Adoption Outcomes

* Weekly Active Operators
* Company Activation Rate
* Mode Adoption Mix

