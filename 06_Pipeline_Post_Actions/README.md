# Jenkins Pipeline Post Actions

The post section defines one or more additional steps that are run upon the completion of a Pipeline’s or stage’s run (depending on the location of the post section within the Pipeline). post can support any of the following post-condition blocks: **always**, **changed**, **fixed**, **regression**, **aborted**, **failure**, **success**, **unstable**, **unsuccessful**, and **cleanup**.

```
pipeline {
    agent any
    stages {
        stage('Example') {
            steps {
                echo 'Hello World'
            }
        }
    }
    post {
        always {
            echo 'I will always say Hello again!'
        }
        failure {
            echo 'I will say Hello again! on failure'
        }
        success {
            echo 'I will say Hello again! on success'
        }
    }
}

```

## What we are doing in Post actions for the Project

Here we can publish reports like Allure Reports, Cucumber Reports in Post actions.
Also, we can configure to send Email notifications in Post actions.

## Pipeline Syntax

Pipeline ships with built-in documentation features "Pipeline Syntax" to make it easier to create Pipelines of varying complexities. This built-in documentation is automatically generated and updated based on the plugins installed in the Jenkins instance.

<img width="369" alt="Step13" src="https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/594ea226-2e77-445b-bf4c-ad85455f5af6">


Click on Snippet Generator, Select step from the list and provide details and generate pipeline syntax.

<img width="2174" alt="Step14" src="https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/919465d1-0b83-4043-af57-7195e148c9dc">
