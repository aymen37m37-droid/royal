# نظام إدارة المطعم المتكامل

## Overview
This project is a comprehensive, offline-first web application for restaurant management. It operates entirely within the browser using HTML5, JavaScript ES6+, CSS3, and IndexedDB, requiring no internet connection or external servers. Its purpose is to provide a robust, secure, and user-friendly solution for managing inventory, employees, suppliers, finances, and point-of-sale operations, specifically designed for local restaurant environments. The application aims to streamline daily operations, enhance financial tracking, and improve overall efficiency for restaurant businesses.

## User Preferences
- I prefer simple and clear language.
- I want iterative development with regular updates.
- Please ask for my confirmation before implementing major changes or new features.
- Ensure all explanations are detailed, especially for complex functionalities.
- Do not make changes to files outside the `js/modules/` directory without explicit approval.

## System Architecture

### UI/UX Decisions
The application features a professional, user-friendly interface with full RTL support for Arabic. It includes responsive design for optimal viewing across desktop, tablet, and mobile devices. A dark mode is fully supported and easily toggleable from the header. The color scheme utilizes Deep Blue, Teal Green, and Amber, with Cairo and Tajawal fonts for clear readability.

### Technical Implementations
The system is built with a modular design, where each functional unit resides in a separate file. It uses an event-driven architecture for interactions and `async/await` for asynchronous operations, ensuring robust error handling. Key functionalities are managed by `db.js` (IndexedDB operations, CRUD, import/export), `utils.js` (helper functions, modals, validation), and `app.js` (application initialization, navigation, theme, notifications).

### Feature Specifications
The application includes a comprehensive set of features:
- **Dashboard:** General statistics, low stock alerts, financial summaries.
- **Inventory Management:** CRUD operations for items, stock movement tracking, audits, waste recording, automatic profit margin calculation, smart alerts, advanced search and filtering.
- **Employee Management:** Full employee records, attendance, salary management (basic, incentives, deductions, advances), shift scheduling.
- **Supplier Management:** Comprehensive supplier database, purchase invoices, payment tracking, debt monitoring, supplier evaluation.
- **Financial System:** Detailed revenue and expense tracking with categories, automatic net profit calculation, financial analysis.
- **Reporting & Statistics:** Extensive reports for inventory, employees, suppliers, and finance, with direct printing capability.
- **Settings:** Dark/light mode toggle, data backup/restore, data deletion, system information.
- **Point of Sale (POS):**
    - **Department POS:** Order items from inventory for different departments, automatic stock deduction, order invoice printing.
    - **Employee Cashier:** Manage meal lists, employee meal orders, automatic deduction from employee accounts, meal invoice printing.
- **Smart Notifications:** Priority-based alerts for low stock, expiring items, low profit margins, high labor costs, high waste ratios, overdue debts, and performance reviews.
- **Enhanced Search:** Search functionality for inventory (name, number, category) and employees (name, number).

### System Design Choices
The application is designed as an Offline-First Progressive Web Application (PWA) with all data stored locally in IndexedDB. This ensures 100% data locality and security, as no data is sent to external servers. The architecture prioritizes performance with instant loading, quick response times, and efficient handling of thousands of records through optimized search and filtering.

## External Dependencies
The project is designed to be entirely self-contained with **no external dependencies**. It utilizes standard web technologies:
- **HTML5**
- **CSS3**
- **JavaScript ES6+**
- **IndexedDB**