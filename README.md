# **[CS427 - Internet of Things] Flask Template**

### **Authors**
Jake Uyechi (uyechi23@up.edu, jake.uyechi@gmail.com)\
Surj Patel (patels@up.edu)

## **Description**
This is a simple Flask app with the minimum required functionality for an Internet of Things (IoT) project. This includes Flask routing, URL parameters, 
Jinja2 HTML templating, and a simple local database using the sqlite3 Python library. Visit the related link to the supplementary ESP32 libraries to find
the wifi_client library that is compatible with this Flask template.

### **Related**
Supplementary CS427 ESP32 IoT Libraries - https://github.com/uyechi23/CS427-IoTLibraries

<br>

## **Setup - Windows**

### **Prerequisites**
- Python
- pip
- git

### **Cloning the repository**
This Flask application will be run on a computer - it will be the server that will host the web application. Any device connected to the same Wi-Fi network can 
connect to the web application, which includes other laptops, phones, and IoT devices.

First, open the Windows Command Prompt. Run the set of following commands to clone the git repository into a local folder (this can be wherever you want to
save your Flask application, but for this example, I chose my desktop):
```
C:\Users\[username]> chdir C:\Users\[username]\Desktop
C:\Users\[username]\Desktop> git clone https://github.com/uyechi23/CS427-FlaskTemplate.git
C:\Users\[username]\Desktop> chdir "CS427-FlaskTemplate.git"
```

Once the files are cloned, you have two choices: remove the git repository, or (if you're familiar with git) change the remote to a personal GitHub repository.

To remove the git repository, run the following command:
```
C:\Users\[username]\Desktop\CS427-FlaskTemplate> rmdir /s .git
```

Once the original .git repository is deleted, you can add it to your own GitHub repository (note that you will need to create a completely empty directory first,
then retrieve the address of the repository):
```
C:\Users\[username]\Desktop\CS427-FlaskTemplate> git init
C:\Users\[username]\Desktop\CS427-FlaskTemplate> git add .
C:\Users\[username]\Desktop\CS427-FlaskTemplate> git commit -m "Initial Commit"
C:\Users\[username]\Desktop\CS427-FlaskTemplate> git branch -M main
C:\Users\[username]\Desktop\CS427-FlaskTemplate> git remote add origin [GitHub repository address]
C:\Users\[username]\Desktop\CS427-FlaskTemplate> git push -u origin main
```

NOTE: GitHub discontinued logging in through HTTPS username/password combinations back in August 2021.
To get around this issue, view the article below to set up a personal access token to be able to push to your GitHub repository:
https://docs.github.com/en/enterprise-server@3.4/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token

### **Setting up a Virtual Environment**
We will need to set up a virtual environment - this allows us to easily set up annd run a lightweight application without needing to always install packages
through pip on every computer. The dependencies for the Flask application are listed in requirements.txt. The following commands are for Windows Command Prompt
and assume you already have Python and pip installed.
```
py -m pip install --user virtualenv
py -m virtualenv env
env\Scripts\activate
pip install -r requirements.txt
```

### **Running and Accessing the Flask App**
Finally, run the Flask app using the following command:
```
flask run -h 0.0.0.0 -p 5000
```

Your Flask app should now be running on a certain socket - you can use a smartphone or other device to verify the Flask app is running by typing the IP address
and port number into a web browser (i.e., 10.17.154.215:5000). Access routes in the Flask app by adding onto the end of the socket (i.e., putting
"10.17.154.215:5000/input/10" in your browser would access the Flask route described by the @app.route("/input/\<value\>") decorator).

To stop the Flask app, either exit the terminal or press CTRL-C.

## **Working with ESP32/Arduino**

### **Supplementary ESP32 Libraries**
Visit https://github.com/uyechi23/CS427-IoTLibraries to find the ESP32 library files that can be used with this Flask app. Use the wifi_client library to connect to
the Flask app.
