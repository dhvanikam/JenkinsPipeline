# Jenkins Pipeline 

## Prerequisites
To use Jenkins Pipeline, we will need:

1. Jenkins 2.x or later.
2. Pipeline plugin.  (Note : which is installed as part of the "suggested plugins", if not installed than got to Dashboard --> Manage Jenkins --> Plugins --> Avialable Plugins, search for "Pipeline" and install plugin)

## Create using Jenkins UI

Step 1: Login to Jenkins and go to home page and click on New Item (+).

<img width="540" alt="Step1" src="https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/56c74bb4-a098-4ecc-b1ea-13ed3632f1fa">



Step 2: Provide name and select "Pipeline" nad press "OK", It will open the Pipeline configuration page.

<img width="1497" alt="Step2" src="https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/6683fc15-771f-43d9-a1be-d7eac8e9d8c1">


Step 3: In Pipeline Configuration page scroll down and Go to Pipeline Section

<img width="1850" alt="Step3" src="https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/8e98b03a-28d4-41f8-ae38-8713bbfe15f8">

Step 4: Enter your Pipeline code into the Script text area.
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

<img width="1537" alt="Step4" src="https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/f84c7dce-8fa4-45d7-b1e7-6fc62ae2c06f">


Step 5: Click on Save.

Step 6: Pipeline project/item view page will open and click on "Build Now" to run pipeline.

<img width="847" alt="Step5" src="https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/24f48654-4805-4462-b76f-4c5c6a0dbd2b">

Step 7: See the stage view of the pipeline after run.

<img width="1479" alt="Step6" src="https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/159d0048-c8a1-4024-a8cf-ef23b06350b6">

Step 8: Under Build History on the left, click #1 to access the details for this particular Pipeline run.

<img width="1537" alt="Step7" src="https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/9044e06a-ae61-4102-9b7e-4e5797e5e6ae">



Note : Defining a Pipeline through the classic UI is convenient for testing Pipeline code snippets, or for handling simple Pipelines or Pipelines that do not require source code to be checked out/cloned from a repository. As mentioned above, Jenkinsfiles entered into the Script text area area of Pipeline projects are stored by Jenkins itself, within the Jenkins home directory. 
