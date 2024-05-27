import tkinter as tk
from email.message import EmailMessage
import smtplib
import time

root = tk.Tk()
root.title("Email Scheduler")

def send_email():
    global msg, email_content, email_address, subject
    email_address = email_entry.get("1.0", tk.END)
    email_content = content_entry.get("1.0", tk.END)
    subject = subject_entry.get()

    msg = EmailMessage()
    msg.set_content(email_content)
    msg['Subject'] = subject
    msg['From'] = #Insert email address
    msg['To'] = email_address

def email_send():
    send_email()
    with smtplib.SMTP_SSL('#Email host', port=#Email port) as s:
        s.login(#Login for email) 
        s.send_message(msg)
        print("Email sent at", time_to_send)
    
def code_running():
    print("The code is runnning")
    check_time()
    
def check_time():
    global time_to_send
    time_to_send = time_entry.get()
    current_time = time.strftime("%H:%M:%S")
    print(current_time, time_to_send, current_time==time_to_send)
    if current_time == time_to_send:
        email_send()
    else:
        root.after(1000, check_time)

# Creation of GUI elements
tk.Label(root, text="To:").pack()
email_entry = tk.Text(root, height=1, width=30)
email_entry.pack()

tk.Label(root,text="From: #Insert email address").pack()

tk.Label(root, text="Email Subject:").pack()
subject_entry = tk.Entry(root)
subject_entry.pack()

tk.Label(root, text="Email Content:").pack()
content_entry = tk.Text(root, height=10, width=50)
content_entry.pack()

tk.Label(root, text="Time to Send (24 hr time):").pack()
time_entry = tk.Entry(root)
time_entry.pack()

send_button = tk.Button(root, text="Schedule Email", command=code_running)
send_button.pack()

root.mainloop()
