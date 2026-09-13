# Build an Email Simulator

## Note: This is provided as a guide only. Do not rely on it to bypass learning—always put in the effort and practice to earn your certification honestly.

---

# CODE

```python
import datetime  # Used to get the current date and time for emails

class Email:
    def __init__(self, sender, receiver, subject, body):
        self.sender = sender              # User object who sent the email
        self.receiver = receiver          # User object who will receive the email
        self.subject = subject            # Subject of the email
        self.body = body                  # Body/content of the email
        self.timestamp = datetime.datetime.now()  # Time when the email was created
        self.read = False                 # Email is unread by default

    def mark_as_read(self):
        self.read = True                  # Updates read status to True

    def display_full_email(self):
        self.mark_as_read()               # Automatically mark email as read
        print('\n--- Email ---')
        print(f'From: {self.sender.name}')
        print(f'To: {self.receiver.name}')
        print(f'Subject: {self.subject}')
        print(f"Received: {self.timestamp.strftime('%Y-%m-%d %H:%M')}")
        print(f'Body: {self.body}')
        print('------------\n')

    def __str__(self):
        status = 'Read' if self.read else 'Unread'
        return (
            f"[{status}] From: {self.sender.name} | "
            f"Subject: {self.subject} | "
            f"Time: {self.timestamp.strftime('%Y-%m-%d %H:%M')}"
        )

class Inbox:
    def __init__(self):
        self.emails = []                  # List to store Email objects

    def receive_email(self, email):
        self.emails.append(email)         # Add email to inbox

    def list_emails(self):
        if not self.emails:               # Check if inbox is empty
            print('Your inbox is empty.\n')
            return

        print('\nYour Emails:')
        for i, email in enumerate(self.emails, start=1):
            print(f'{i}. {email}')        # Uses Email.__str__()

    def list_emails(self):
        if not self.emails:               # Check if inbox is empty
            print('Your inbox is empty.\n')
            return

        print('\nYour Emails:')
        for i, email in enumerate(self.emails, start=1):
            print(f'{i}. {email}')        # Uses Email.__str__()

    def read_email(self, index):
        if not self.emails:
            print('Inbox is empty.\n')
            return

        actual_index = index - 1          # Convert to zero-based index
        if actual_index < 0 or actual_index >= len(self.emails):
            print('Invalid email number.\n')
            return

        self.emails[actual_index].display_full_email()

    def delete_email(self, index):
        if not self.emails:
            print('Inbox is empty.\n')
            return

        actual_index = index - 1
        if actual_index < 0 or actual_index >= len(self.emails):
            print('Invalid email number.\n')
            return

        del self.emails[actual_index]     # Remove email from inbox
        print('Email deleted.\n')

class User:
    def __init__(self, name):
        self.name = name                  # User's name
        self.inbox = Inbox()              # Each user has their own inbox

    def send_email(self, receiver, subject, body):
        email = Email(
            sender=self,                  # Current user is the sender
            receiver=receiver,            # Receiver is another User
            subject=subject,
            body=body
        )
        receiver.inbox.receive_email(email)  # Deliver email
        print(f'Email sent from {self.name} to {receiver.name}!\n')

    def check_inbox(self):
        print(f"\n{self.name}'s Inbox:")
        self.inbox.list_emails()

    def read_email(self, index):
        self.inbox.read_email(index)

    def delete_email(self, index):
        self.inbox.delete_email(index)

def main():
    tory = User('Tory')                   # Create user Tory
    ramy = User('Ramy')                   # Create user Ramy

    # Tory sends an email to Ramy
    tory.send_email('Ramy', 'Hello', 'Hi Ramy, just saying hello!')

    # Ramy replies to Tory
    ramy.send_email('Tory', 'Re: Hello', 'Hi Tory, hope you are fine.')

if __name__ == '__main__':
    main()
```

# Email System Code Explanation

This Python program simulates a simple email system with **users**, **inboxes**, and **emails**, including features like sending, reading, listing, and deleting emails.

---

## 1. `Email` Class

The `Email` class represents an individual email message.

### Attributes
- `sender` – The `User` object sending the email.
- `receiver` – The `User` object receiving the email.
- `subject` – The subject line of the email.
- `body` – The main content of the email.
- `timestamp` – Automatically records the date and time when the email was created using `datetime.datetime.now()`.
- `read` – Boolean to indicate if the email has been read. Defaults to `False`.

### Methods
- `mark_as_read()`  
  Marks the email as read by setting `read = True`.

- `display_full_email()`  
  Prints the full details of the email (sender, receiver, subject, timestamp, and body) and marks it as read.

- `__str__()`  
  Returns a short summary of the email for listing purposes, showing read/unread status, sender, subject, and timestamp.

---

## 2. `Inbox` Class

The `Inbox` class represents a user's inbox containing all received emails.

### Attributes
- `emails` – A list that stores all `Email` objects received by the user.

### Methods
- `receive_email(email)`  
  Adds a new `Email` object to the `emails` list.

- `list_emails()`  
  Lists all emails in the inbox with enumeration. Prints “Your inbox is empty” if there are no emails.

- `read_email(index)`  
  Reads and displays the full content of an email by its index in the inbox. Validates the index before access.

- `delete_email(index)`  
  Deletes an email at the specified index after validating it. Prints confirmation upon deletion.

---

## 3. `User` Class

The `User` class represents a system user who can send and receive emails.

### Attributes
- `name` – The name of the user.
- `inbox` – Each user has their own `Inbox` object to store received emails.

### Methods
- `send_email(receiver, subject, body)`  
  Creates a new `Email` object and sends it to the receiver's inbox. Prints confirmation of the sent email.

- `check_inbox()`  
  Prints the list of emails in the user's inbox using `Inbox.list_emails()`.

- `read_email(index)`  
  Reads a specific email from the inbox by calling `Inbox.read_email(index)`.

- `delete_email(index)`  
  Deletes a specific email from the inbox by calling `Inbox.delete_email(index)`.

---

## 4. Main Function

The `main()` function demonstrates the system in action:

```python
tory = User('Tory')
ramy = User('Ramy')        

# Tory sends an email to Ramy
tory.send_email(ramy, 'Hello', 'Hi Ramy, just saying hello!')

# Ramy replies to Tory
ramy.send_email(tory, 'Re: Hello', 'Hi Tory, hope you are fine.')
```

---

### What Happens

1. Two users are created: Tory and Ramy.
2. Tory sends an email to Ramy → added to Ramy’s inbox → confirmation printed.
3. Ramy replies to Tory → added to Tory’s inbox → confirmation printed.

---

## 5. Program Execution

```python
if __name__ == '__main__':
    main()
```
- Ensures that main() runs only when the script is executed directly.
- Sets up the user simulation and email exchange.

---

## Key Features Implemented

- Email creation with timestamp and read/unread status
- Inbox management: receive, list, read, delete emails
- Users can send emails to each other
- User-friendly output with confirmation messages and full email display
