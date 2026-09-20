# MediBook: Online Doctor Appointment System TESTING PLAN

MediBook is a centralized, web-based appointment management system designed to simplify the scheduling process between patients and healthcare providers. The platform reduces manual booking difficulties by allowing users to discover doctor availability, book and reschedule appointments, manage prescriptions, and receive appointment reminders.

## Key Features

### Patient Registration & Authentication

* 11-digit Bangladeshi mobile number validation
* Email format validation
* OTP-based account verification
* CAPTCHA after multiple failed attempts
* Temporary account lockout after repeated failed login attempts

### Doctor Search & Filtering

* Search doctors by medical specialization
* Filter doctors by location
* Filter by rating
* Filter by consultation fee range
* Dynamic doctor search and filtering

### Real-Time Appointment Booking

* View available appointment slots
* Prevent double booking
* Reserve available slots
* Automatically release cancelled appointment slots

### Automated Notifications

* SMS appointment confirmations
* Email appointment confirmations
* Automated appointment reminders

### Prescriptions & Digital Medical Records

* Doctor-side electronic prescription uploads
* PDF prescription management
* Patient medical document uploads
* Support for lab reports and X-rays
* Access to patient medical history before consultation

### Role-Based Dashboards

**Doctors**

* Manage visiting schedules
* View upcoming appointments
* Mark consultations as completed
* Access patient medical history

**Administrators**

* Add and verify doctor credentials
* Manage doctor schedules and consultation fees
* View and manage appointments
* Generate analytical reports

---

## Tech Stack

| Category            | Technologies              |
| ------------------- | ------------------------- |
| Frontend            | React.js                  |
| Backend             | Node.js, Express.js       |
| Database            | PostgreSQL                |
| Payment Gateway     | bKash / Nagad Payment API |
| Test Automation     | Selenium WebDriver        |
| Performance Testing | Apache JMeter             |
| Manual Testing      | Exploratory Testing       |
| Version Control     | Git, GitHub               |

---

## System Quality Standards

### Availability

* Target monthly uptime: **≥ 99.5%**
* Planned maintenance window: **1:00 AM – 3:00 AM BST**

### Performance

* Doctor search and schedule pages should load within **3 seconds** under normal conditions.
* System is designed to support up to **2,000 active users** under the defined test conditions.
* Appointment confirmations should be processed within **5 seconds**.

### Security

* Encryption for sensitive patient information
* Role-Based Access Control (RBAC)
* Secure handling of medical records and prescriptions
* Protection of patient National ID (NID) information

### Usability

* Core appointment actions designed around a simple **3-click workflow**
* Responsive interface supporting screen widths down to **360px**

---

# QA Test Execution & Deliverables

**Test Plan ID:** `SQT-C04`

### Testing Scope

The project covers:

* Unit Testing
* System Testing
* Integration Testing
* End-to-End Testing
* User Acceptance Testing (UAT)
* Manual Exploratory Testing
* Automated Functional Testing
* Performance and Load Testing

## Test Summary Matrix

| Test ID | Module              | Test Title                                              | Status |
| ------- | ------------------- | ------------------------------------------------------- | ------ |
| TC-1    | Authentication      | Patient Registration with OTP Verification              | ❌ Fail |
| TC-2    | Authentication      | Block Registration with Invalid Email and Phone Formats | ✅ Pass |
| TC-3    | Authentication      | Account Lockout on Failed Logins                        | ✅ Pass |
| TC-4    | Search & Discovery  | Search Doctors by Specialization                        | ❌ Fail |
| TC-5    | Search & Discovery  | Filter Doctors by Location and Consultation Fee         | ✅ Pass |
| TC-6    | Search & Discovery  | View Doctor Profile Details                             | ✅ Pass |
| TC-7    | Appointment Booking | Book Appointment with Available Time Slot               | ✅ Pass |
| TC-8    | Appointment Booking | Prevent Double Booking                                  | ❌ Fail |
| TC-9    | Appointment Booking | Cancel Appointment and Release Time Slot                | ✅ Pass |
| TC-10   | Records Management  | Doctor Uploads Electronic Prescription                  | ✅ Pass |
| TC-11   | Records Management  | Doctor Views Patient Medical History                    | ✅ Pass |
| TC-12   | Records Management  | Patient Uploads Medical Reports and Documents           | ✅ Pass |
| TC-13   | Admin Dashboard     | Admin Adds a New Doctor                                 | ✅ Pass |
| TC-14   | Doctor Dashboard    | Doctor Manages Availability Schedule                    | ✅ Pass |
| TC-15   | Admin Dashboard     | Admin Views Appointments and Generates Reports          | ❌ Fail |

### High-Priority Defects

The following defects were identified during testing:

1. OTP delivery failure during patient registration
2. Empty results when searching by medical specialization
3. Race-condition issue allowing double booking
4. Report data truncation in the admin dashboard

---

# Out-of-Scope Items

The following areas were excluded from the testing scope:

1. Internal processing and delivery reliability of third-party SMS and email gateways
2. Internal banking and transaction verification logic of payment gateways
3. ISP reliability and external network infrastructure
4. Verification of the factual accuracy of medical licenses and academic credentials
5. Medical diagnostic decision-making algorithms

---

# Getting Started

## Prerequisites

Make sure the following are installed:

* Node.js `v18.x` or higher
* PostgreSQL `v14.x` or higher
* npm or Yarn

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/medibook.git
cd medibook
```

### 2. Backend Setup

```bash
cd backend
npm install
cp .env.example .env
```

Configure the required environment variables in `.env`:

```env
PORT=
DATABASE_URL=
JWT_SECRET=
```

Start the backend:

```bash
npm run dev
```

### 3. Frontend Setup

Open a new terminal:

```bash
cd frontend
npm install
npm start
```

### 4. Run Automated Tests

Run the Selenium end-to-end test suite:

```bash
npm run test:e2e
```

---

# Project Information

**Institution:** American International University-Bangladesh (AIUB)

**Department:** Department of Computer Science, Faculty of Science & Technology (FST)

**Course:** Software Quality Assurance and Testing, Section C

**Supervising Faculty / Manager:** Saikat Baul

## Project & QA Team

| Member             | Student ID   | Role                            |
| ------------------ | ------------ | ------------------------------- |
| Mahin Sarker       | `22-48338-3` | Project Manager / QA Tester     |
| Fahim Rahman Talha | `22-48437-3` | Product Manager / QA Tester     |
| Rayhan Chowdhury   | `22-48420-3` | Development Manager / QA Tester |
| Tanni Rani Nath    | `22-48430-3` | Test Manager / QA Tester        |
| Dipaneeta Pramanik | `22-48286-3` | Account Manager / QA Tester     |

---

## Testing Tools

This project uses the following tools and technologies for quality assurance:

* **Selenium WebDriver** for automated functional and regression testing
* **Apache JMeter** for performance and load testing
* **Jira** for defect tracking and issue management
* **Manual Exploratory Testing** for usability and functional validation
* **Git/GitHub** for version control and collaboration

---

## Project Highlights

* Web-based healthcare appointment management
* Role-based access for patients, doctors, and administrators
* Real-time appointment scheduling
* Digital prescription and medical document management
* Automated functional testing with Selenium
* Performance testing with Apache JMeter
* Structured test cases and defect tracking
* Database-driven application architecture
