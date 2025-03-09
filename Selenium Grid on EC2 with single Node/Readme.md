## 1. Setting Up Selenium Grid

**Code:**

```python
sudo apt update

sudo apt install default-jre

#download standalone selenium

wget https://selenium-release.storage.googleapis.com/3.141/selenium-server-standalone-3.141.59.jar

# Start the Selenium Grid Hub on your EC2 instance.

java -jar selenium-server-standalone-3.141.59.jar -role hub

```
**Successfuly Installed Selenum Grid on EC2:**

![Code Execution](https://i.imgur.com/OyicuQI.png)

## 2. Running a Test Suite in Parallel

**Code:**

```python
from selenium import webdriver
import time

# Define the capabilities (browser, platform)
capabilities = {
    "browserName": "chrome",
    "platform": "LINUX"
}

options = webdriver.ChromeOptions()
options.set_capability("browserName", "chrome")
options.set_capability("platform", "LINUX")

# Start the browsers, make sure to replace your Public IPs
driver1 = webdriver.Remote(
    command_executor='http://172.31.19.249:4444/wd/hub',
    options=options
)

driver2 = webdriver.Remote(
    command_executor='http://172.31.19.249:4444/wd/hub',
    options=options
)

# Close the browsers
time.sleep(5)
driver1.quit()
driver2.quit()
```
**Code Execution:**

![Code Execution](https://i.imgur.com/83MwL8G.png)

![Code Execution](https://i.imgur.com/fKpTqN2.png)
