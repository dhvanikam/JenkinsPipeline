# Jenkins Pipeline Through SCM

## Setup Project in IDE and put the Jenkinsfile in project

Here i am using Eclipse,

  <img width="417" alt="Step5" src="https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/6b2f36dd-51e3-4b7c-bd41-6645271acba8">


**Jenkinsfile**
```
pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'Pre-build'
            }
        }
        stage('Unit tests') {
            steps {
                echo 'Running unit tests'
            }
        }
        stage('deploy') {
            steps {
                echo 'Deploying build'
            }
        }
        stage('Regression tests') {
            steps {
                echo 'Running E2E tests'
            }
        }
        stage('Release to prod') {
            steps {
                echo 'Releasing to prod'
            }
        }
    }
 post {
        always {
            echo 'Cleanup after everything!'
        }
    }
}
```

## Setup Git and GitHub with Jenkins

1. Go to Dashboard --> Manage Jenkins --> Plugins --> Available plugins
2. Search for "Git" and install Git plugins on Jenkins.
3. Search for "GitHub" and install GitHub plugins on Jenkins.
4. Install and restart Jenkins.
5. Go to credentials manager in Jenkins and add username and password for GitHub Dashboard --> Manage Jenkins --> Credentials --> System --> Global credentials.
6. Make sure Jenkinsfile is committed into the project Repository.

## Configure "Pipeline script from SCM"

To configure your Pipeline project to use a Jenkinsfile from source control:

Follow the previouse mentioned steps till Step 3.

Step 4: Select option Pipeline - Definition as "Pipeline script from SCM"

  <img width="1537" alt="Step6" src="https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/9e23765a-e90b-4f12-8944-3f052d5e82ea">

Step 5: From the SCM field, choose the type of source control system of the repository containing your Jenkinsfile, Here I have mentioned Git and provided details.

  <img width="1891" alt="Step7" src="https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/edf21dfc-5633-410c-b8b5-ae2b9f31b39e">

Step 6: Make sure "Jenkinsfile" mention in "Script Path"

  <img width="1846" alt="Step8" src="https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/f846556c-5046-43f2-aa9a-6eae60b2782c">

When you update the designated repository, a new build is triggered, as long as the Pipeline is configured with an SCM polling trigger.


  




