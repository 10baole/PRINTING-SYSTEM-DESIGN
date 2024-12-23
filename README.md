# Student Smart Printing Service (HCMUT_SSPS)

This repository contains the implementation of the **Student Smart Printing Service (HCMUT_SSPS)**, a web-based application designed to facilitate document printing for students across university campuses. The system supports printer management, printing history tracking, and account-based printing page limits with features for purchasing additional pages.

## Features

### Student Features
1. **Document Printing**
   - Upload document files to the system.
   - Choose a printer and configure printing properties such as:
     - Paper size (A4, A3).
     - Pages to be printed.
     - Single-/double-sided printing.
     - Number of copies.
   - Ensure the number of pages does not exceed the student’s page balance.
2. **Printing Logs**
   - View personal printing history for a selected date range.
   - Summary of printed pages for each paper size.
3. **Buy Printing Pages**
   - Purchase additional printing pages through the university’s BKPay online payment system.
   - A3 pages are counted as equivalent to two A4 pages.

### SPSO Features
1. **Printer Management**
   - Add new printers with details such as ID, brand, model, description, and location (campus, building, room).
   - Enable or disable printers.
2. **System Configuration Management**
   - Configure the default number of pages for students each semester.
   - Define dates for allocating default pages to all students.
   - Manage permitted file types for document uploads.
3. **Printing Logs and Reports**
   - View logs for all students or specific students, filtered by date range and printer.
   - Access automatically generated reports of system usage at the end of each month and year.

### Authentication
All users (students and SPSO) must authenticate through the **HCMUT_SSO** authentication service before accessing the system.

## System Components
1. **Printers**
   - Each printer has attributes: ID, brand, model, description, and location.
   - Managed by the SPSO.
2. **Printing Logs**
   - Tracks each printing action with details:
     - Student ID and Printer ID.
     - File name.
     - Printing start and end time.
     - Number of pages for each page size.
3. **User Accounts**
   - Tracks page balances for each student.
   - Handles page purchase transactions.

## Technical Requirements
1. **Web-based Application**
   - The system is accessible through a browser.
2. **Authentication**
   - Integrated with **HCMUT_SSO** for secure user authentication.
3. **Payment Integration**
   - Supports payments through **BKPay**, the university’s online payment system.

## Usage Instructions

### For Students
1. Log in using your university credentials through the HCMUT_SSO service.
2. To print a document:
   - Upload the file.
   - Select a printer and configure the printing properties.
   - Ensure sufficient page balance.
3. To view printing logs:
   - Navigate to the "My Printing History" section.
   - Filter by date range.
4. To buy printing pages:
   - Go to the "Buy Pages" section.
   - Complete the payment through BKPay.

### For SPSO
1. Log in using your administrative credentials.
2. Manage printers:
   - Add, enable, or disable printers.
3. Configure system settings:
   - Modify default page allocations, allocation dates, and permitted file types.
4. View reports and logs:
   - Navigate to the "Reports" section.
   - Filter by time period or printer.

## Development Details

### Tech Stack
- **Frontend**: HTML, CSS, JavaScript (React or similar framework).
- **Backend**: Python (Django/Flask) or Node.js.
- **Database**: PostgreSQL/MySQL for managing users, printers, and logs.
- **Authentication**: Integrated with HCMUT_SSO.
- **Payment Gateway**: Integration with BKPay API.

### Deployment
1. Install dependencies listed in `requirements.txt`.
2. Set up the database and apply migrations.
3. Configure authentication and payment settings.
4. Run the application server.

### Configuration Files
- `config.py`: Includes settings for default pages, BKPay integration, and file type permissions.

## Contribution Guidelines
1. Fork the repository and create a new branch for your feature or bug fix.
2. Ensure code adheres to project standards.
3. Submit a pull request with a clear description of your changes.

## License
This project is licensed under the MIT License. See the `LICENSE` file for more details.

## Acknowledgments
This project was developed to support students and staff at HCMUT, ensuring efficient and user-friendly access to printing services.

