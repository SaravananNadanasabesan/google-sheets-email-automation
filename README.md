# 📌 Google Sheets to Email Automation with Make.com  

## 📖 Overview  
This project demonstrates how to automate workflows using **Make.com (formerly Integromat)**.  
The scenario listens for **new rows in a Google Sheet** and automatically sends a **formatted HTML email** with the new entry details.  

### 🔧 Use Cases  
- Automating recruitment outreach logs  
- Sending notifications for new form responses  
- Creating lightweight ETL notifications (data captured → instant alerts)  

---

## 🛠️ Tech Stack  
- **Google Sheets** → Data input source  
- **Make.com** → Automation platform (no-code/low-code integration)  
- **Email (SMTP/IMAP via Outlook/Gmail)** → Notification channel  

---

## 🔄 Workflow Architecture  

**Trigger:**  
- Module: **Google Sheets – Watch New Rows**  
- Action: Listens for any new rows added in the spreadsheet (headers: *Name, LinkedIn URI, Category*).  

**Action:**  
- Module: **Email – Send an Email**  
- Sends a formatted HTML email with mapped values from the row.  

---

## 📊 Example Input (Google Sheet)  

| Name          | LinkedIn URI                                | Category |
|---------------|---------------------------------------------|----------|
| Manush Parikh | https://www.linkedin.com/in/manush-parikh/  | Manager  |
| Dheeraj Chouhan | https://www.linkedin.com/in/dheeraj-chouhan/ | Cloud & DevOps |

---

## 📧 Example Output (Email)  

**Subject:** Google Sheet Update – New Row Added  

**Body (HTML):**

```html
<h3 style="color:#2E86C1;">Google Sheet Update</h3>
<p>Hello Saravanan,</p>
<p>A new row was added in your sheet. Here are the details:</p>
<ul>
  <li><b>Name:</b> Manush Parikh</li>
  <li><b>Email:</b> https://www.linkedin.com/in/manush-parikh/</li>
  <li><b>Designation:</b> Manager</li>
</ul>
<p style="color:gray;">This is an automated email from Make.com</p>

Result in Mailbox:

Name: Manush Parikh

Email: https://www.linkedin.com/in/manush-parikh/

Designation: Manager

🚀 How to Reproduce

Create a Google Sheet with headers: Name | LinkedIn URI | Category

In Make.com:

Add Google Sheets – Watch New Rows.

Add Email – Send Email (SMTP/Outlook/Gmail).

Map each column into the HTML body.

Turn the scenario ON and set scheduling interval (e.g., every 15 minutes).

Add a row in Google Sheets → Email notification is sent automatically.

📂 Repository Structure
📦 google-sheets-email-automation
 ┣ 📜 README.md      # Project documentation
 ┣ 📂 screenshots    # Workflow + output screenshots
 ┃ ┣ workflow.png
 ┃ ┗ email_result.png
 ┗ 📜 LICENSE

🌟 Key Learnings

Hands-on with low-code/no-code automation.

Integrated multiple services using APIs behind the scenes.

Built a real-world automation pipeline: data entry → transformation → notification.

🔮 Future Improvements

Send WhatsApp Business Cloud notifications in addition to email.

Archive processed rows into another sheet.

Add error handling & logging.

Extend notifications to Slack/Teams.
