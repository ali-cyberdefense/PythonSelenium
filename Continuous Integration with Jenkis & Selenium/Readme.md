## 1. Installing Jenkis 

**Code:**

```python
url -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins

sudo apt update
sudo apt install openjdk-17-jre
java -version

sudo apt install openjdk-8-jdk
java --version

sudo systemctl enable jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins
 
```
**Jenkis Installation**

![Code Execution](https://i.imgur.com/KigtVPh.png)

![Code Execution](https://i.imgur.com/yI4IfOb.png)

## 2. Connection with Github 

**Code:**

```python
from selenium import webdriver
import time
driver = webdriver.Chrome()
driver.get("https://aws.amazon.com/")
time.sleep(5)
driver.quit()

#Open PyCharm Terminal...

git config --global user.name <Github username>
git config --global user.email <Github email>

#for push you need ssh key
goto ssh key
generate ssh key
ssh-keygen -t ed25519 -C "usamaaslam2017@gmail.com"
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_ed25519
cat ~/.ssh/id_ed25519.pub

#Now open github account in the browser
copy the key from terminal 
Goto setting and then new ssh key
Give key name e.g., usama
paste key here

#Go back to PyCharm Terminal and type following commands 
git init
git add . or git add -A
git commit -m "first commit"
git status


Open browser and create public git repository
#use push commands from there to push main/master repo to the repository

Integrating Jenkins with Selenium
open Jenkins in browser
<Public IP of EC2>:8080

Goto PyCharm terminal and type
cat /var/lib/jenkins/secrets/initialAdminPassword

Copy the key and paste in browser to login jenkins
Create Admin user and password at first login

#Install necessary plugins
In the Jenkins dashboard, go to "Manage Jenkins" > "Manage Plugins" and install the necessary plugins, including the Selenium plugin.

#Create a New Jenkins Job
Click on "New Item" in the Jenkins dashboard.
Enter a name for the job (e.g., SeleniumTestJob) and select "Freestyle project". Click "OK".

Configure the Jenkins Job:

Under "Source Code Management", choose your version control system (e.g., Git).
In the "Build" section, add a build step to execute your Selenium tests.

# Navigate to your project directory
cd /home/ubuntu/PycharmProjects/pythonProject
# Activate your virtual environment
source /home/ubuntu/PycharmProjects/pythonProject/bin/activate
# Run your Selenium tests
python selenium_tests.py


Save the Configuration.

Trigger the Job:
In the Jenkins dashboard, find your job (SeleniumTestJob) and click "Build Now" to trigger a build.

 
```
**Execution**

![Code Execution](https://i.imgur.com/o9KnfQa.png)

![Code Execution](https://i.imgur.com/np4gtB8.png)

![Code Execution](https://i.imgur.com/hcnGulh.png)
