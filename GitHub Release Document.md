# Breeder Management App — Unified SQL Express & SQL Server Edition
## Initial GitHub Release — Version 1.0.0

This release introduces the fully unified version of the Breeder Management App, combining all features and license tiers into a single Windows `.exe` application. The app supports both SQL Express and SQL Server, selected during installation, eliminating the need for separate builds or database versions.

All license tiers (Basic, Pro, Enterprise) are included in one unified application, with access determined by the user’s Gumroad license key.

---

## Role‑Based Access Control (RBAC)
All AIAI applications now include a unified, secure RBAC system designed for multi‑admin breeding operations and professional data governance.

Global Admin  
Full system access. Can configure company‑wide settings, manage assistants, control data sources, and access all modules.

Assistant  
Operational access only. Can manage animals, heat cycles, pairings, litters, puppies, buyers, and vaccinations. Cannot modify global settings or create new companies.

Breeder
Hands‑on operational role focused solely on animal‑related tasks. Breeders can manage animals, heat cycles, pairings, litters, puppies, vaccinations, reminders, and whelping‑related tools. They cannot access business modules, financial tools, marketing, reports, or any administrative settings. Breeders do not manage assistants, do not configure company settings, and cannot access global or company‑wide controls.

Admin‑Only Registration  
Only administrators can register accounts. No breeder, buyer, or assistant self‑registration is allowed.

Dynamic UI Permissions  
Each screen automatically adapts to the user’s role. Restricted modules are hidden or blocked with clear access messages.

Centralized Permission Enforcement  
All role checks are handled through a unified RBAC engine to ensure consistent security across every module and workflow.

Multi‑Admin Support  
Global Admin customers can add additional assistants (subject to plan limits). Each assistant receives their own secure login and role‑based access.

This RBAC system ensures secure, scalable, and professional‑grade access control across all AIAI applications.

---

## Included in This Release
- Basic Plan  
- Pro Plan  
- Enterprise Plan  
- Assistant Add‑on (role‑based, plan‑limited)  
- Unified SQL Express + SQL Server architecture  
- One installer, one app, one onboarding flow  

---

## Plan Descriptions

### Basic Plan
Provides essential management features for small or hobby breeders.  
Includes core tools for managing breeders, animals, puppies, buyers, vaccinations, and reminders.  
Ideal for users who need a reliable, cost‑effective foundation.

---

### Pro Plan
Expands on the Basic plan with advanced breeding workflow tools.  
Designed for growing kennels that manage multiple animals and litters.  
Includes:
- Heat cycle tracking  
- Pairings  
- Whelping forecast  
- Litters  
- Deposits  
- Expenses  
- Genetic risk (COI) analysis  

---

### Enterprise Plan
Unlocks the full capabilities of the system, including everything in Pro plus enterprise‑grade controls.  
Required for organizations with multiple administrators or complex operational needs.

Enterprise includes:
- Advanced reporting  
- Marketing suite  
- Contract automation  
- Priority support  
- Enhanced analytics  

---

### Assistant Add‑on
Allows Global Admins to add additional assistants (limit based on plan).  
Ensures secure, individual login access without shared credentials.  
Cannot function alone — requires an active Basic, Pro, or Enterprise plan.

---

## License Activation
This app requires a valid Gumroad license key to unlock full functionality.

- You will be prompted to enter your license key on first launch.  
- The app verifies your key securely via Gumroad’s API.  
- If the license is invalid or revoked, access will be restricted.  
- Internet access is required for initial license validation.

After activation, the app operates fully offline.

---

## Database
The Breeder Management App supports two database modes, selected during installation:

### SQL Express (Local Database — Recommended for 1–5 users)
- Automatically installed and configured by the installer  
- Ideal for individuals, small kennels, and single‑machine setups  
- Fully offline and self‑contained  

### SQL Server (Remote or On‑Prem Server)
- Connect to an existing SQL Server instance  
- Supports multi‑user environments and IT‑managed deployments  
- Ideal for medium‑to‑large kennels or companies with dedicated servers  

Both modes use the same unified application and feature set.

---

## Stability
This version is the current stable build distributed through the updater and serves as the foundation for all future updates.
