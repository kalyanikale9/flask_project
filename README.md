Procedure
 To install Visual Studio Code on CentOS, follow these steps.
Method 1: Install from Microsoft's repository

1. Import the Microsoft GPG key
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

2. Add the VS Code repository
Create the repository file:
sudo tee /etc/yum.repos.d/vscode.repo > /dev/null <<EOF
[code]
name=Visual Studio Code
baseurl=https://packages.microsoft.com/yumrepos/vscode
enabled=1
gpgcheck=1
gpgkey=https://packages.microsoft.com/keys/microsoft.asc
EOF

3. Install VS Code
sudo yum install code
or
sudo dnf install code

4 . Launch VS Code
code
        or
code --no-sandbox --user-data-dir=/tmp/vscode-root

Verify Python Installation
 python3 --version
If Python is not installed on CentOS
   sudo dnf install python3 -y
Verify installation again.
   python3 --version

Verify pip Installation
pip --version
If pip is not installed:
sudo dnf install python3-pip -y

Create Virtual Environment
python3 -m venv venv

Install Flask
     pip install flask
Verify installation.
flask --version

Create Flask Application
Create a file on VS code
      app.py
Write the following code.
from flask import Flask
app = Flask(__name__)

@app.route('/')
def home():
    return "Welcome to Flask Web Application"
if __name__ == '__main__':
    app.run(debug=True)


Save the file.
Run Application
app.py

Output
Welcome to Flask Web Application
