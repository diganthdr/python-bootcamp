### **Chapter: Sending Emails in Python**

Sending emails is a common task in various applications, from simple notifications to more complex communication systems. Python provides several libraries to send emails, with `smtplib` being the most widely used built-in library for this purpose.

In this chapter, we will cover:
1. **Overview of SMTP**
2. **Using Python's `smtplib`**
3. **Sending a Simple Email**
4. **Sending Emails with Attachments**
5. **Using Third-Party Email Libraries**
6. **Securing Email Sending (SSL/TLS)**
7. **Practice Exercises**

---

### **1. Overview of SMTP**

SMTP (Simple Mail Transfer Protocol) is the protocol used to send emails over the internet. In Python, the `smtplib` module is used to send mail using the SMTP protocol.

Key components:
- **SMTP Server**: The mail server that sends and receives emails. Common examples include Gmail's SMTP server, Yahoo's SMTP server, etc.
- **Email Format**: Emails typically include a subject, body, and sender/receiver addresses.

---

### **2. Using Python’s `smtplib`**

Python’s `smtplib` module provides the functionality to establish an SMTP connection and send emails. To send an email, you need:
- SMTP server address (e.g., Gmail: `smtp.gmail.com`)
- Port (usually 587 for TLS or 465 for SSL)
- Your email credentials (username, password)

### **3. Sending a Simple Email**

#### **Step-by-Step Code Example:**

```python
import smtplib
from email.mime.text import MIMEText
from email.mime.multipart import MIMEMultipart

# Step 1: Set up the SMTP server
smtp_server = "smtp.gmail.com"
port = 587  # For TLS
sender_email = "your_email@gmail.com"
receiver_email = "receiver_email@gmail.com"
password = "your_password"

# Step 2: Create the email content
subject = "Hello from Python!"
body = "This is a test email sent from Python."

# Create a multipart message
message = MIMEMultipart()
message["From"] = sender_email
message["To"] = receiver_email
message["Subject"] = subject

# Attach the body of the email
message.attach(MIMEText(body, "plain"))

# Step 3: Establish a connection and send the email
try:
    # Connect to the server
    server = smtplib.SMTP(smtp_server, port)
    server.starttls()  # Secure the connection

    # Login to the email account
    server.login(sender_email, password)

    # Send the email
    server.sendmail(sender_email, receiver_email, message.as_string())
    print("Email sent successfully!")
except Exception as e:
    print(f"Error: {e}")
finally:
    # Close the connection
    server.quit()
```

### **Explanation:**
- **MIMEMultipart**: Used to create a multipart message that can have multiple parts (e.g., plain text, attachments).
- **MIMEText**: Allows you to attach text to your email body.
- **starttls()**: Establishes a secure connection using TLS.

---

### **4. Sending Emails with Attachments**

To send an email with attachments, we need to modify the email structure to include the file in the MIME format.

#### **Example:**

```python
import smtplib
from email.mime.text import MIMEText
from email.mime.multipart import MIMEMultipart
from email.mime.base import MIMEBase
from email import encoders

smtp_server = "smtp.gmail.com"
port = 587
sender_email = "your_email@gmail.com"
receiver_email = "receiver_email@gmail.com"
password = "your_password"

subject = "Email with Attachment"
body = "Please find the attached file."

# Create a multipart message
message = MIMEMultipart()
message["From"] = sender_email
message["To"] = receiver_email
message["Subject"] = subject

# Attach the body of the email
message.attach(MIMEText(body, "plain"))

# Attach a file
filename = "document.pdf"  # Path to the file

# Open the file in binary mode
with open(filename, "rb") as attachment:
    # Add file as application/octet-stream
    part = MIMEBase("application", "octet-stream")
    part.set_payload(attachment.read())

# Encode file in ASCII characters to send by email    
encoders.encode_base64(part)

# Add header as key/value pair to the attachment part
part.add_header("Content-Disposition", f"attachment; filename= {filename}")

# Add attachment to message
message.attach(part)

# Send the email
try:
    server = smtplib.SMTP(smtp_server, port)
    server.starttls()
    server.login(sender_email, password)
    server.sendmail(sender_email, receiver_email, message.as_string())
    print("Email with attachment sent successfully!")
except Exception as e:
    print(f"Error: {e}")
finally:
    server.quit()
```

### **Explanation:**
- **MIMEBase**: Allows us to attach non-text files (like PDFs, images).
- **encoders.encode_base64**: Encodes the file to ensure it is safely sent over the network.
- **Content-Disposition**: Used to specify that the attached file should be treated as an attachment.

---

### **5. Using Third-Party Email Libraries**

There are other libraries that make sending emails easier:
- **yagmail**: A simple and easy-to-use library for sending Gmail messages.
- **Flask-Mail**: A useful extension for sending emails in Flask applications.

#### **Example using `yagmail`:**

```bash
pip install yagmail
```

```python
import yagmail

yag = yagmail.SMTP("your_email@gmail.com", "your_password")

# Send a simple email
yag.send("receiver_email@gmail.com", "Subject Line", "Email Body")
```

---

### **6. Securing Email Sending (SSL/TLS)**

When sending emails, it’s important to ensure a secure connection using SSL or TLS. You can use the `smtplib.SMTP_SSL` class for SSL encryption.

#### **Example with SSL:**

```python
import smtplib

smtp_server = "smtp.gmail.com"
port = 465  # SSL port
sender_email = "your_email@gmail.com"
receiver_email = "receiver_email@gmail.com"
password = "your_password"

subject = "SSL Secured Email"
body = "This email is sent using SSL encryption."

message = f"Subject: {subject}\n\n{body}"

try:
    server = smtplib.SMTP_SSL(smtp_server, port)
    server.login(sender_email, password)
    server.sendmail(sender_email, receiver_email, message)
    print("Email sent using SSL!")
except Exception as e:
    print(f"Error: {e}")
finally:
    server.quit()
```

---

### **7. Practice Exercises**

1. **Send a Birthday Reminder Email**:
   Write a Python script that sends a reminder email on your friend’s birthday. Include their name in the subject line and body.

2. **Send a Weekly Report Email**:
   Automate sending a weekly report email with an attached CSV file containing data. Use `pandas` to create the CSV file before sending it.

3. **Create an Email Notification System**:
   Create a notification system that sends an email whenever a certain event occurs, such as when a file is added to a directory.

4. **Send an HTML Formatted Email**:
   Write a Python script that sends an email with HTML content. Create a simple HTML template for the email body.

---

### **Conclusion**

By the end of this chapter, you should now understand how to send emails in Python using `smtplib`. You learned how to send simple emails, emails with attachments, secure the connection using SSL/TLS, and even explored third-party libraries like `yagmail`. With the provided exercises, you can practice building real-world applications that send emails.

Next, we can move to automation with email scheduling and handling received emails for a more complete understanding of email handling in Python.
