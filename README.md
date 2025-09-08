Automated Employee Time-Off Management System

## 📋 Project Overview
This project automates employee time-off management using Airtable (database) and Zapier (automation), built to meet a Product Requirement Document (PRD). It streamlines leave request submissions, manager approvals, employee notifications, and PTO balance tracking (22 days annually, resetting yearly). The system reduces manual effort and ensures accurate data, showcasing no-code automation skills.
✨ Features

Time-Off Application: Employees submit requests via an Airtable form (dates, days, notes).
Manager Notification: Managers receive emails with request details and Approve/Reject links.
Approval Workflow: Managers approve/reject requests via webhook links, updating status.
Employee Notification: Employees get email updates on request status (Approved/Rejected).
Leave Balance Management: Approved requests deduct from PTO balances; balances reset annually.

🛠️ Tech Stack

Airtable: Stores employee and request data in a no-code database.
Zapier: Automates workflows (notifications, approvals, balance updates).
Gmail: Sends notifications (configurable with other email providers).

📂 Setup
Airtable

Base: Created "Time-Off Management" with two tables:
Employees: Fields: Name (text), Email (email), Manager (linked), PTO Balance (number, default 22), Last Reset Date (date).
Leave Requests: Fields: Employee (linked), Start Date (date), End Date (date), Number of Days (formula: DATETIME_DIFF({End Date}, {Start Date}, 'days') + 1), Notes (text), Status (Pending/Approved/Rejected), Manager Comments (text), Manager Email (lookup).


Form: Configured a form in Leave Requests for employees to submit requests.
Fix: Resolved Manager Email not populating by correcting the Lookup field (Employee → Manager → Email).

Zapier
Five Zaps automate the workflow:
Notify Manager: Triggers on new Leave Requests record → Sends email with request details and webhook links.
Approve Request: Webhook → Updates Status to Approved, deducts PTO Balance.
Reject Request: Webhook → Updates Status to Rejected.
Notify Employee: Triggers on Status change → Emails employee with update.
Yearly Reset: Scheduled yearly → Resets PTO Balance to 22.


Fix: Ensured Manager Email was mapped correctly in notification Zap.

Screenshots

Employees table: screenshots/employees-table.png
Leave Requests form: screenshots/leave-requests-form.png
Zapier Zap 1: screenshots/zapier-notify-manager.png

🚀 How to Run

Clone the Repository:
git clone https://github.com/chaisoman/employee-time-off-automation.git


Set Up Airtable:

Create a base using sample-employees.csv and Technical_Documentation.md.
Configure tables and form as described.


Set Up Zapier:

Follow Technical_Documentation.md to create the five Zaps.
Connect Airtable and Gmail accounts.


Test:

Submit a request via the Airtable form.
Verify manager email, approve/reject actions, employee notification, and balance update.



🎥 Demo
https://www.loom.com/share/5fbab44f664f45b8b4512e96c84b89e0

🧩 Challenges and Solutions
Challenge: Manager Email field not populating.
Solution: Fixed Lookup field in Airtable and ensured valid manager links in Employees table.
Challenge: Zapier free plan task limits (100/month).
Solution: Optimized testing to stay within limits.

🔮 Future Improvements
Sync approved requests to Google Calendar.
Add leave types (e.g., Sick, Vacation) for better tracking.
Create a manager dashboard with Airtable Interfaces.
Use Slack instead of email for notifications.

📚 Resources

Technical Documentation: Detailed setup guide.
Airtable Support: For database setup.
Zapier Help: For automation troubleshooting.

Built by Gershom Torkuma Sylvester, 
September 2025
# Employee-Time-Off-Automation
Automated employee time-off management system using Airtable and Zapier.
