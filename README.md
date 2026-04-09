# ITGC Audit – Live E-commerce Platform (Case Study)

##  Executive Overview

This project presents an end-to-end IT General Controls (ITGC) assessment performed on a live e-commerce platform  used for customer bookings and payment processing.

The objective of this audit was to evaluate the effectiveness of key control domains including access management, data protection, change management, logging and monitoring, and third-party risk.

The assessment was conducted using a risk-based audit approach and reflects a real-world governance, risk, and compliance (GRC) evaluation scenario.

---

##  Audit Objectives

The primary objectives of this assessment were:

- Evaluate the design and effectiveness of IT General Controls (ITGC)
- Identify risks related to unauthorized access and data exposure
- Assess the handling and protection of personal identifiable information (PII)
- Evaluate change management and deployment practices
- Assess logging and monitoring capabilities
- Identify gaps in third-party risk management
- Provide practical remediation recommendations

---

##  Scope of Assessment

The assessment covered the following components:

### In Scope

- Web application (customer booking and checkout flow)
- Backend services and API endpoints
- MongoDB database storing customer data
- Environment variable and secrets handling
- Deployment and version control practices (GitHub)
- Logging mechanisms (Winston-based logging)
- Third-party integrations:
  - Payment processing (Stripe)
  - Email service (Gmail SMTP)
  - Media storage (Cloudinary)

### Out of Scope

- Network-level security controls
- Infrastructure hardening
- Full penetration testing
- Internal controls of third-party providers (e.g., Stripe)

---

##  Methodology

The audit was conducted following a structured ITGC assessment approach:

1. System Understanding & Architecture Review  
2. Data Flow and PII Identification  
3. Access Control Analysis (User & System Access)  
4. Risk Identification and Risk Register Development  
5. Control Design (ITGC Control Matrix, SoD, UAR)  
6. Control Testing with Evidence Collection  
7. Findings Documentation  
8. Remediation Planning  

All findings were validated through direct system observation and supporting evidence.

---

##  Key Findings

### 1. Lack of Authentication Controls
The system allows users to perform booking and checkout operations without authentication, increasing the risk of unauthorized access and lack of accountability.

---

### 2. Absence of Role-Based Access Control (RBAC)
No authentication or authorization middleware is implemented to enforce role-based access restrictions. Administrative routes are not protected through access control logic.

---

### 3. Excessive Privileged Access
Developers have unrestricted access to system components including database, deployment environment, and sensitive configuration, creating a high risk of misuse or insider threats.

---

### 4. Inconsistent Encryption of PII
While certain sensitive fields (email, contact number) are encrypted, other personal data (name, address, company) are stored in plaintext, indicating inconsistent control implementation.

---

### 5. Weak Secrets Management
Sensitive credentials (e.g., database connection strings, API keys) are stored in environment variables and are accessible within the development environment without access restrictions.

---

### 6. Lack of Change Management Controls
Changes are committed directly to the main branch without pull request review, approval workflow, or environment segregation, increasing the risk of untested changes reaching production.

---

### 7. Insufficient Logging and Monitoring
System-level logging exists; however, no logging is implemented for user activity, authentication events, or administrative actions, limiting auditability and incident investigation capabilities.

---

### 8. Lack of Third-Party Risk Management
No evidence of vendor risk assessment, external audit, or compliance certification was identified, indicating a lack of formal third-party governance.

---

##  Control Areas Evaluated

The following ITGC domains were assessed:

- Access Control (Authentication, Authorization, RBAC)
- Data Protection (PII Handling, Encryption)
- Change Management (Code Deployment & Version Control)
- Logging & Monitoring (Audit Logging)
- Third-Party Risk Management

---

##  Framework Alignment

This assessment aligns with industry-recognized frameworks:

- NIST Cybersecurity Framework (CSF)
  - PR.AC (Access Control)
  - PR.DS (Data Security)
  - PR.IP (Processes)
  - DE.CM (Monitoring)
  - ID.SC (Supply Chain Risk)

- ISO/IEC 27001
  - Access Control
  - Cryptography
  - Operations Security
  - Logging & Monitoring
  - Supplier Relationships

---

##  Deliverables

The following audit deliverables were produced:

- Project Charter  
- System & Data Flow Analysis  
- Risk Register  
- ITGC Control Matrix  
- User Access Review (UAR)  
- Segregation of Duties (SoD) Analysis  
- Testing Workpapers  
- Findings Log  
- Remediation Tracker  
- Evidence Repository  

---

##  Evidence-Based Testing

All control deficiencies were validated through direct evidence, including:

- Application behavior screenshots  
- Code-level inspection (VS Code)  
- GitHub repository analysis  
- Logging output review  

Evidence is organized in the `/07_Evidence` directory and mapped to each test case.

---

##  Disclaimer

This project is a personal audit case study conducted for educational and portfolio purposes.

All sensitive information has been removed or masked. No real credentials, customer data, or confidential information are exposed.

---

##  Author

Ali Riza Sevgili  
Cybersecurity | GRC | IT Risk  
Toronto, Canada
