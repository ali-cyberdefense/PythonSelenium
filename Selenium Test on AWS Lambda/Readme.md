## Taking Screenshot & Upload on S3

**Code:**

```python
Creating Layers in Lambda
create new folder name it as lambda selenium

Open terminal in this folder
pip3.7 install selenium==3.8.0 -t python/lib/python3.7/site-packages
pip3.7 install -t selenium/python/lib/python3.7/site-packages selenium==3.8.0

Run these commands make sure to have python3.7 installed.

#now zip this folder and name it e.g., selenium

Uploading Selenium to Lambda Layer
now goto lambda --> layers
create layer
selenium
upload your zip here
x86_64
Runtimes Python3.7
create layer

Now open terminal for creating zip of Chrome browser and Headless Chromium
curl -SL https://chromedriver.storage.googleapis.com/2.37/chromedriver_linux64.zip > chromedriver.zip

curl -SL https://github.com/adieuadieu/serverless-chrome/releases/download/v1.0.0-41/stable-headless-chromium-amazonlinux-2017-03.zip > headless-chromium.zip

zip both these together after unzipping them and rename to chromedriver

Uploading chrome drivers to Lambda Layer
now goto lambda --> layers
create layer
chromedriver
upload the zip here
x86_64
Runtimes Python3.7
create layer

Creating Lambda Function
goto lambda, function , create new function
selenium
python3.7
x86_64
create function

Configuring Lambda Function memory for smooth sailing
goto configuration
general configuration
memory to 1024
timeout 1 minutes
save


now click code
scroll down and click edit in Runtime settings
handler put filename.main #in our case it will be like e.g., main.main
save


Adding layers we created to Lambda Function
now click add layer
custom layer
selenium
version 1
add
again click add layer
custom layer
chromedriver
version 1
add

```
**Creating Main.py File**
![Code Execution](https://i.imgur.com/LBzwi6A.png)

**Creating Functions**
![Code Execution](https://i.imgur.com/ZCdp3ph.png)

**Setting up handler & Function Name**
![Code Execution](https://i.imgur.com/C93flbK.png)

**Uploading the Main.py**
![Code Execution](https://i.imgur.com/HomUTFd.png)

**Successful Execution**
![Code Execution](https://i.imgur.com/7seQ5al.png)
