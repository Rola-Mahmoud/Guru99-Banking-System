# Guru99-Banking-System


## Overview

This repository contains the quality assurance deliverables produced by **Team 1** for the **Guru99 Banking Web Application** (`demo.guru99.com`). The project covers manual test case design, execution, and bug reporting across all functional modules of the banking system, spanning both **Manager** and **Customer** roles.

## Demo
[Demo on linkedin](https://www.linkedin.com/posts/rola-mahmoud_manualtesting-qa-softwaretesting-activity-7474585678970859520-COjf?utm_source=social_share_send&utm_medium=member_desktop_web&rcm=ACoAAFGy024ByGzpiKwvLDyDZNqotihDCZvomb0)
---

## Project Structure



```text
Guru99-Banking-System-Testing
│
├── 01_Requirements
│   ├── Team_1_Questionnaire.xlsx
│   ├── SRS_v1.docx
│   ├── SRS_v2.docx
│   ├── SRS_v3.docx
│   └── SRS_v4.docx
│
├── 02_Test_Cases
│   ├── Team_1_TCs_V1.xlsx
│   ├── Team_1_TCs_V2.xlsx
│   ├── Team_1_TCs_V3.xlsx
│   └── Team_1_TCs_V4.xlsx
│
├── 03_Bug_Reports
│   ├── Team_1_Bugs_V1.xlsx
│   ├── Team_1_Bugs_V2.xlsx
│   ├── Team_1_Bugs_V3.xlsx
│   └── Team_1_Bugs_V4.xlsx
│
└── README.md
```

---

## System Under Test

| Attribute       | Details                                         |
|-----------------|-------------------------------------------------|
| Application     | Guru99 Banking System                           |
| URL             | `http://demo.guru99.com`                        |
| Browser         | Google Chrome v27 or later                      |
| User Roles      | Manager, Customer                               |

---

## Modules Tested

### Manager Role

| Module                        | TC Sheet Name                    |
|-------------------------------|----------------------------------|
| Login & Logout                | Manger Login & Logout            |
| New Customer                  | New Customer                     |
| Edit Customer                 | Edit Customer                    |
| Delete Customer               | Delete Customer                  |
| New Account                   | New Account                      |
| Edit Account                  | Edit Account                     |
| Delete Account                | Delete Account                   |
| Balance Enquiry               | Manager Balance Enquiry          |
| Fund Transfer                 | Manager Fund Transfer            |
| Customized Statement          | Manager Customized Statement     |
| Change Password               | Manager Change Password          |
| Deposit                       | Deposit                          |
| Withdrawal                    | Withdrawal                       |

### Customer Role

| Module                        | TC Sheet Name                    |
|-------------------------------|----------------------------------|
| Login & Logout                | Customer Log in & Logout         |
| Balance Enquiry               | Customer Balance Enquiry         |
| Fund Transfer                 | Customer Fund Transfer           |
| Mini Statement                | Customer Mini Statement          |
| Customized Statement          | Customer Customized Statement    |
| Change Password               | Customer Change Password         |

> **Note:** At the start of V1 testing, the following modules were identified as blocked and could not be fully tested: Balance Enquiry, Fund Transfer, Withdrawal, and Customer Login & Logout. These were flagged in the `List of Blocked Modules` sheet of `Team_1_TCs_V1.xlsx`.

---

## Test Case Structure

Each test case entry in the TC files contains the following fields:

| Field            | Description                                               |
|------------------|-----------------------------------------------------------|
| TC ID            | Unique test case identifier (e.g., `TC_Bank_MGR_BE_005`) |
| Title            | Short name of the scenario                                |
| Description      | What the test verifies                                    |
| Precondition     | State required before test execution                      |
| Steps            | Step-by-step actions to perform                           |
| Test Data        | Input values used during execution                        |
| Designed By      | Team member who authored the test case                    |
| Priority         | High / Medium / Low                                       |
| Expected Result  | What the system should do                                 |
| Status           | Pass / Fail / Blocked                                     |
| Actual Result    | What the system actually did                              |
| Requirement ID   | Traceability to the source requirement                    |

---

## Bug Report Structure

Each bug entry in the Bug files contains the following fields:

| Field                | Description                                                    |
|----------------------|----------------------------------------------------------------|
| Bug ID               | Unique bug identifier (e.g., `Bug_Bank_MGR_BE_001`)           |
| Related TC           | One or more TC IDs that exposed this bug                       |
| Description          | Clear summary of the defect                                    |
| Precondition         | Environment and state required to reproduce                    |
| Steps To Reproduce   | Numbered reproduction steps                                    |
| Test Data            | Exact credentials and input values used                        |
| Priority             | Business impact: High / Medium / Low                           |
| Severity             | Technical impact: Critical / High / Medium / Low               |
| Designed By          | Team member who reported the bug                               |
| Assigned To          | Developer responsible for the fix                              |
| Expected Result      | Correct system behavior                                        |
| Actual Result        | Observed (incorrect) system behavior                           |
| Attachments          | Screenshots or Screen recordings (links where available)       |
| Status               | Open / In Progress / Resolved / Closed                         |

---

## Version History

### Test Cases

| Version | Key Changes                                                                              |
|---------|------------------------------------------------------------------------------------------|
| V1      | Initial test cases across all 20 modules; blocked modules flagged                        |
| V2      | Revised and refined test case coverage based on initial execution feedback                |
| V3      | Further updates based on review; expanded boundary and negative scenarios                |
| V4      | Final version; all feedback incorporated; ready for sign-off                             |

### Bug Reports

| Version | Modules Covered                                                                                                         |
|---------|-------------------------------------------------------------------------------------------------------------------------|
| V1      | Manager Customized Statement, New Customer, New Account, Edit Account                                                   |
| V2      | + Manager Balance Enquiry, Edit Customer, Delete Customer                                                               |
| V3      | + Customer Balance Enquiry, Customer Fund Transfer, Customer Customized Statement, Manager Change Password, Login/Logout|
| V4      | Final consolidated version — all V3 modules; credentials cleaned from Balance Enquiry bugs; Fund Transfer bugs refined  |

---

## Key Bugs Summary

The following are the most critical (High Priority / Critical Severity) bugs identified across all versions:

| Bug ID                  | Module                          | Summary                                                              |
|-------------------------|---------------------------------|----------------------------------------------------------------------|
| `Bug_Bank_MGR_BE_001`   | Manager Balance Enquiry         | Valid account balance enquiry redirects to error page instead of displaying results |
| `Bug_Bank_MGR_BE_005`   | Manager Balance Enquiry         | Unauthorized account access redirects to blank page instead of showing validation message |
| `Bug_Bank_MGR_CS_003`   | Manager Customized Statement    | Valid statement query redirects to blank page instead of displaying results |
| `Bug_Bank_MGR_CS_004`   | Manager Customized Statement    | Invalid date range redirects to blank page instead of showing validation error |
| `Bug_Bank_CUST_BE_003`  | Customer Balance Enquiry        | Linked account balance enquiry returns "This page isn't working" error |
| `Bug_Bank_CUST_FT_003`  | Customer Fund Transfer          | Transfer from another customer's account is not rejected (authorization bypass) |
| `Bug_Bank_CUST_FT_005`  | Customer Fund Transfer          | Same-account transfer is not rejected; no validation message shown   |
| `Bug_Bank_CUST_FT_006`  | Customer Fund Transfer          | Zero and negative amounts are accepted without validation             |
| `Bug_Bank_MGR_NC_001`   | New Customer                    | Valid customer submission returns HTTP 500 Internal Server Error      |
| `BUG_Bank_CUST_CS_001`  | Customer Customized Statement   | Valid statement submission redirects to blank white screen            |
| `BUG_Bank_MGR_CP_003`   | Manager Change Password         | Successful password change redirects to blank page instead of logging out |

---

## Test Credentials Used

> ⚠️ **Note:** These are demo environment credentials for the Guru99 test application only. Do not use in any production system.

| Role     | Username      | Password    |
|----------|---------------|-------------|
| Manager  | `mngr661915`  | `EzYzypY`   |
| Customer | `73061`       | `123456`    |

---

## Team Members

| Name         | Contributions                                                                                           |
|--------------|---------------------------------------------------------------------------------------------------------|
| Rola         | Manager Balance Enquiry, Manager Customized Statement, Customer Balance Enquiry, Customer Fund Transfer |
| Karen        | Manager New Account, Manager Edit Account, Manager Withdrawl, Customer Login & Logout                   |
| Omar         | Manager Fund Transfer, Delete Account, Manger Login & Logout, Customer Change Password                  |
| Moamen       | New Customer, Edit Customer, Delete Customer, Customer Mini Statement                                   |
| Abdelrahman  | Customer Customized Statement, Manager Change Password, Manager Deposit                                 |

---

## How to Use These Files

1. **Open** the relevant TC or Bug file in Microsoft Excel or Google Sheets.
2. **Navigate** to the sheet corresponding to the module you want to review.
3. **Filter** by Status (Pass / Fail / Blocked) or Priority to focus on specific areas.
4. **Cross-reference** Bug IDs with TC IDs using the `Related TC` column in bug reports to trace defects back to test cases.
5. **Track progress** across versions by comparing the same module's sheet between V1 → V4.

---

## Notes

- All bugs are currently marked **Open** and assigned to the Developer role for resolution.
- Some bugs span multiple test cases — these are grouped under a single Bug ID to avoid duplication and clearly map the scope of the defect.
- The most common failure pattern observed is **blank/error page redirection** when the system should either display results or show a validation message — this appears to be a systemic backend issue on `demo.guru99.com`.
