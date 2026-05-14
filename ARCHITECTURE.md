# Breeder Management App – Architecture Overview

## Overview
The Breeder Management App is a closed‑source Windows `.exe` application built for offline operation, secure license enforcement, and automated reporting. It provides a fast, local Operational CRM tailored specifically for professional dog breeding programs. Unlike cloud‑based CRMs, the system runs entirely on the user’s machine or internal network, ensuring reliability, data ownership, and zero external dependencies.

The application supports both SQL Server Express and Full SQL Server, selected during installation.

---

# Architecture

## Role‑Based Access Control (RBAC)
All AIAI applications include a unified, secure RBAC system designed for multi‑admin breeding operations.

### Global Admin
Full system access. Can configure company‑wide settings, manage assistants, control data sources, and access all modules.

### Assistant
Operational access only. Can manage animals, heat cycles, pairings, litters, puppies, buyers, and vaccinations. Cannot modify global settings or create new companies.

### Breeder
Hands‑on operational role focused solely on animal‑related tasks. Breeders can manage animals, heat cycles, pairings, litters, puppies, vaccinations, reminders, and whelping‑related tools. They cannot access business modules, financial tools, marketing, reports, or any administrative settings. Breeders do not manage assistants, do not configure company settings, and cannot access global or company‑wide controls.

### Admin‑Only Registration
Only administrators can register accounts. No breeder, buyer, or assistant self‑registration is allowed.

### Dynamic UI Permissions
Each screen automatically adapts to the user’s role. Restricted modules are hidden or blocked with clear access messages.

### Centralized Permission Enforcement
All role checks are handled through a unified RBAC engine to ensure consistent security across every module and workflow.

### Multi‑Admin Support
Global Admins can add additional assistants (subject to plan limits). Each assistant receives their own secure login and role‑based access.

This RBAC system ensures secure, scalable, and professional‑grade access control across the entire breeding operation.

---

## Database Selection (Installer‑Driven)

During installation, the user selects one of two supported database modes:

### 1. SQL Server Express (Local Database – Recommended for 1–5 Users)
- Installer automatically installs and configures SQL Server Express
- Ideal for single‑machine setups or small breeding programs
- No licensing cost

### 2. Full SQL Server (Standard/Enterprise)
- User connects to an existing SQL Server instance
- Supports multi‑user environments and IT‑managed deployments
- Designed for medium to large kennels or multi‑location operations

The installer writes a registry flag (`UseSQLExpress`) that determines which connection setup page the application loads on first launch.

---

## License Enforcement Flow
User Launch → License Prompt → Gumroad API Validation → Local Unlock

- User enters their Gumroad license key on first launch
- Key is validated through Gumroad’s `/v2/licenses/verify` endpoint
- Valid keys unlock the application and store the license state locally
- Periodic revalidation may occur (e.g., every 7 days)
- License tier determines access to Basic, Pro, or Enterprise features

---

## Local Session Context
- All data is stored in SQL Server Express or Full SQL Server
- No cloud sync, Redis, or external session store
- Secure login using salted + hashed admin credentials
- Fully offline operation after initial license activation

---

## Data Transfer Between Computers
The app includes a built‑in SQL migration tool for moving data to a new machine:

- Creates a `.bak` backup file from the old computer
- Restores the `.bak` file on the new computer
- Works for both SQL Express and Full SQL Server
- Ideal for machine upgrades or office migrations

---

## SQL Connection Pages
The application routes users to the correct connection setup page based on installer selection:

- `sql_connection_page.py` – SQL Express
- `sql_server_connection_page.py` – Full SQL Server

Both pages support:
- Connection testing
- Credential validation
- Database creation (if needed)
- Secure admin login setup

---

# Breeding Workflow Architecture

Admin Login → Heat Cycle Tracking → Pairings → Whelping Forecast → Litters → Puppies → Buyers → Contracts

---

## Heat Cycle Tracking
- Log heat cycle stages
- Predict fertile windows
- Trigger reminders

## Pairings
- Record sire/dam pairings
- Auto‑calculate expected whelp dates
- Integrates with genetic risk engine (COI)

## Genetic Risk Engine
- Placeholder COI calculation
- Future‑ready for full pedigree analysis
- Integrated into pairings and reports

## Whelping Forecast
- Uses SQL Server date math (61–65 day window)
- Flags due‑soon and overdue litters
- Generates forecast reports

## Litters
- Track birth events
- Record puppy counts, notes, complications

## Puppies
- Track weights, photos, status, microchips
- Assign puppies to buyers

## Buyers & Deposits
- Manage buyer profiles
- Track deposits and reservation status

## Contracts
- Auto‑generate adoption contracts
- Enterprise‑only advanced templates

## Vaccinations
- Track puppy vaccinations
- Auto‑calculate next due dates
- Generate vaccination records

## Expenses
- Track breeding‑related expenses
- Categorize for tax and reporting

---

# File Storage & Export

All reports are stored locally under:

Documents/AIAI_Breeder_App/Exports/YYYY-MM/

Exports include:
- Whelping Forecast PDFs
- Vaccination Records
- Litter Reports
- Puppy Reports
- Expense Reports
- Marketing PDFs (Enterprise)

