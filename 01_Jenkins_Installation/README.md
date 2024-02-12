# Jenkins Installtion on macOS

Jenkins can be installed using the Homebrew package manager. Homebrew formula: jenkins-lts This is a package supported by a third party which may be not as frequently updated as packages supported by the Jenkins project directly.

## Sample commands:
Install the latest LTS version:
```
brew install jenkins-lts
```
Start the Jenkins service:
```
brew services start jenkins-lts
```
Restart the Jenkins service:
```
brew services restart jenkins-lts
```
Update the Jenkins version: 
```
brew upgrade jenkins-lts
```

After starting the Jenkins service, browse to http://localhost:8080 and follow the instructions to complete the installation.

### Step 1: When you first access a new Jenkins instance, you are asked to unlock it using an automatically-generated password.

Browse to http://localhost:8080 (or whichever port you configured for Jenkins when installing it) and wait until the Unlock Jenkins page appears.


### Step 2: From the Jenkins console log output, copy the automatically-generated alphanumeric password 

The command: ```sudo cat /var/lib/jenkins/secrets/initialAdminPassword``` will print the password at console.

### Step 3: Customizing Jenkins with plugins
After unlocking Jenkins, the Customize Jenkins page appears. Here you can install any number of useful plugins as part of your initial setup.

Click one of the two options shown:

**_Install suggested plugins_** - to install the recommended set of plugins, which are based on most common use cases.

**_Select plugins to install_** - to choose which set of plugins to initially install. When you first access the plugin selection page, the suggested plugins are selected by default.

If you are not sure what plugins you need, choose Install suggested plugins.

### Step 4: Creating the first administrator user
Finally, after customizing Jenkins with plugins, Jenkins asks you to create your first administrator user.

When the Create First Admin User page appears, specify the details for your administrator user in the respective fields and click Save and Finish.

When the Jenkins is ready page appears, click Start using Jenkins.
