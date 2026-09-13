# 🐍 What Is Python and What Are Some Common Uses in the Industry?

Python is a general-purpose programming language known for its simplicity and ease of use. This ease of use has made Python the most popular programming language in modern times. In 2024, Python officially surpassed JavaScript as the most popular language on GitHub.

Python is used in many fields like **data science and machine learning**, **web development**, **scripting and automation**, **embedded systems**, **IoT**, and much more.

---

## 📊 Data Science and Machine Learning

Python is the main language that most data scientists and machine learning engineers currently use. Libraries like **Pandas** and **NumPy** make data analysis less tedious, while others like **TensorFlow** and **Scikit-learn** make machine learning and working with AI models much more accessible.

---

## 🌐 Web Development

In web development, Python frameworks like **Django**, **FastAPI**, and **Flask** let developers build scalable and secure backend systems with minimal effort. Many social media platforms like **Instagram** and **Pinterest** use Python on the backend.

---

## 🛡️ Cybersecurity

Cybersecurity professionals and ethical hackers use Python to detect vulnerabilities like malware and other viruses, build automated security scans, and analyze threats.

---

## 💡 Embedded Systems and IoT

Python runs well on microcomputers like the **Raspberry Pi** and MicroPython-compatible boards, so you can build all kinds of IoT projects like smart home devices, weather monitoring stations, and more.

---

## ⚙️ Automation

One of Python's biggest strengths is automation. You can write simple scripts to help you with repetitive tasks like extracting data from spreadsheets, sending emails, and working with files on your local machine.

Libraries like **Selenium** and **BeautifulSoup** also make it easy to interact with websites, so you can scrape public data, automate tasks through a web UI, and even manage cloud deployments for your projects.

---

Python is a very powerful language, and yet, it's easy to learn. From simple automation scripts to large-scale, industrial-level applications, you can use Python for just about anything.

Python is a great choice for anyone who wants to learn programming, regardless of what they choose to specialize in later.

---

# 🖥️ How Do You Install, Configure and Use Python in Your Local Environment?

In the last lesson, you learned what Python is and what you can do with it. Now, let's look into how you can set up Python on your local machine.

The easiest way to install Python on Windows and Mac is to download the installer from the official Python website. We'll also go over running Python on Linux later in this lesson.

Go to [https://www.python.org/](https://www.python.org/) and hover over **Downloads**. A modal will appear showing the current version of Python for your operating system (OS).

---

## 🍎 Installing Python on macOS

1. Click on the button showing the current version of Python (from the previous modal), and you'll start downloading a `.pkg` installation file automatically.  
2. Once the `.pkg` installer is finished downloading, open it, then click **Continue** in the window that opens up.  
3. Continue clicking the **Continue** button until you get to the **Installation Type** section. There, click the **Install** button.  
4. Enter your password if necessary, then start the installation.  
5. After that, you should get a congratulations message saying that Python has been successfully installed.  
6. Click the **Close** button, and you're done!  

You can verify the installation by opening up your terminal and running:

```bash
python --version
# or
python3 --version
```

You can also open the Python interpreter by running:

```bash
python
# or
python3
```

---

A terminal is a text-based interface that lets you interact with your computer by typing commands. Each operating system comes with a default terminal app. On macOS, you can use the Terminal app. On Windows, you can use Command Prompt or PowerShell. On Linux, each desktop environment has its own default terminal app, like **GNOME** Terminal or **Konsole**.

> Note: On some older macOS and Linux systems, python can be reserved for Python 2, while python3 is for Python 3 specifically. If you run `python --version` and see a version of Python 2 like Python 2.7.18, then you should use `python3` going forward. Python 2 is end-of-life and should not be used for any new development.

---

## 🪟 Installing Python on Windows

1. Go to [https://www.python.org/](https://www.python.org/), and hover over **Downloads**. You should see a modal that says Download for Windows and a download button with the current version of Python.
2. Click on the version number, and you'll start downloading a Windows executable (.exe) file automatically.'
3. Once you've finished downloading the Python installer for Windows, double-click on it, and follow the instructions.
4. When you see the option Add python.exe to Path, check that option, then click Install Now. Doing that will make things easier for you later.

You can verify the installation by opening up a command line shell like PowerShell and running:
```powershell
python --version
```

You can also open the Python interpreter by running:
```powershell
python
```

---

## 🐧 Installing Python on Linux

Most major distros like Ubuntu, Debian, and Fedora come with Python installed.

Just open a terminal and run:
```bash
python --version
# or
python3 --version
```

If either command doesn't show a version of Python, you can search for an installation package for your flavor of Linux at [https://www.python.org](https://www.python.org), or search online for the recommended way to install Python for your distro.
