Breeder Management App - User Guide
====================================
Version: 1.0.0

Welcome to the Automating Innovating AI Breeder Management App — a streamlined, secure, and intuitive tool 
for managing breeders, animals, heat cycles, pairings, litters, puppies, buyers, contracts, vaccinations, 
expenses, whelping forecasts, and reporting.

This version includes full RBAC (Role-Based Access Control) and subscription plan enforcement.

RBAC & PLAN ENFORCEMENT (NEW)
------------------------------
The application now includes centralized RBAC and plan-based feature access:

• Role-Based Access Control (RBAC)
  - Every module checks the logged-in user’s role before granting access.
  - Roles include:
      • Global Admin
      • Assistant
      • Breeder
  - Unauthorized users are blocked from restricted modules.

• Subscription Plan Enforcement
  - Features are unlocked based on your subscription tier:
      • BASIC — Core features (animals, breeders, puppies, buyers, vaccinations, reminders)
      • PRO — Adds pairings, litters, deposits, expenses, genetic risk analysis, whelping forecast
      • ENTERPRISE — All features including:
            - Advanced reporting
            - Marketing suite
            - Contract automation
            - Enhanced analytics
  - If a user attempts to access a feature outside their plan, the app will redirect them to the Start Page.

• Session Verification
  - All sensitive modules require an active, verified session.
  - Sessions expire on logout or exit.

Key Features
------------
• Secure Login:
  - Encrypted password protection with industry-standard hashing.
  - RBAC-based access to all modules.

• Breeder & Animal Management:
  - Track breeders, animals, lineage, registration numbers, microchips, colors, and health notes.
  - Manage active and retired animals.

• Heat Cycle Tracking:
  - Log heat cycle stages.
  - Predict fertile windows.
  - Receive reminders for upcoming cycles.
  - Requires BASIC or higher.

• Pairings (PRO+):
  - Record pairings with dates and notes.
  - Automatic whelping date forecasting.
  - Genetic COI (Coefficient of Inbreeding) analysis.
  - Requires PRO or ENTERPRISE plan.

• Whelping Forecast (PRO+):
  - Predict whelping windows (days 61–65).
  - Track due-soon and overdue litters.
  - Generate whelping forecast reports.

• Litters & Puppies (PRO+):
  - Track litters from birth to adoption.
  - Manage puppy details, weights, photos, and status.
  - Assign puppies to buyers.

• Buyer & Deposit Management:
  - Track buyer information and communication.
  - Manage deposits and reservation status.
  - Generate contracts and adoption documents.
  - Deposits require PRO+.

• Vaccination Tracking:
  - Log vaccinations per puppy.
  - Auto-calculate next due dates.
  - Generate vaccination records and health reports.
  - Available on BASIC+.

• Expense Tracking (PRO+):
  - Record breeding-related expenses.
  - Categorize costs for tax and reporting purposes.

• Contracts (ENTERPRISE):
  - Generate adoption contracts and agreements.
  - Auto-fill buyer and puppy information.

• Reporting (ENTERPRISE):
  - Generate PDF reports for litters, puppies, expenses, vaccinations, and whelping forecasts.
  - Enterprise plan includes advanced analytics and marketing reports.

• Marketing Suite (ENTERPRISE):
  - Generate marketing materials for litters and puppies.
  - Export social media content and promotional PDFs.

• Friendly Interface:
  - Designed for ease of use—no technical knowledge required!

System Requirements
-------------------
• Operating System: Windows 10 or later is required.
• PDF viewer recommended for report viewing.
• At least 900 MB of available local disk space is recommended:
    - Data is stored using the client's SQL Server Database.
    - Reports and exports are saved locally.

License Activation
------------------
This app requires a valid Gumroad license key to unlock full functionality.
• You will be prompted to enter your license key on first launch.
• The app verifies your key securely via Gumroad’s API.
• If the license is invalid or revoked, access will be restricted.
Note: Internet access is required for initial license validation.

Getting Started
---------------
1. Launch the app via the Breeder Management App icon.
2. Click 'Admin Registration' to create an account.
3. After registering, click 'Admin Login' to sign in.
4. Navigate to the Admin Interface.
5. Access modules based on your RBAC role and subscription plan.

Navigation & Exiting
---------------------
• Use the dashboard to access key modules.
• Click the 'Exit' button on any screen to close the app.

Tips
----
• Export reports regularly to back up your records.
• Use strong admin credentials.
• Keep animal and breeder data up to date.
• Ensure your subscription plan matches your workflow needs.

Troubleshooting
---------------
• App won’t launch: Ensure Windows 10+ is installed.
• License key rejected: Double-check your Gumroad purchase email.
• Access denied: Check your RBAC role and subscription plan.
• Missing features: Verify your subscription tier.
• Auto-update not working: Check your internet connection and firewall settings.

Support
-------
Questions or feedback? Contact the developer:
automatinginnovatingai@outlook.com

Thank you for using the Breeder Management App!
