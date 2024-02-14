# Jenkins Pipeline

## Sequential Stages
Stages in Declarative Pipeline may have a stages section containing a list of nested stages to be run in sequential order.

<img width="2168" alt="Step17" src="https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/cad355fb-922c-4655-9a29-e053899ff043">


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

## Parallel Stages
Stages in Declarative Pipeline may have a parallel section containing a list of nested stages to be run in parallel.


<img width="2168" alt="Step16" src="https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/228d270d-5fe9-4220-896c-0e98e9f2514f">





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
            parallel {
                stage('Test On chrome') {
                    steps {
                        withMaven(maven:'MyMaven') {
                            sh 'mvn test -Dbrowser=chrome'
                        }
                    }
                    post {
                        always {
                            allure includeProperties: false, jdk: '', results: [[path: 'allure-results']]
                        }
                    }
                }
                stage('Test On firefox') {
                    steps {
                        withMaven(maven:'MyMaven') {
                            sh 'mvn test -Dbrowser=chrome'
                        }
                    }
                    post {
                        always {
                            allure includeProperties: false, jdk: '', results: [[path: 'allure-results']]
                        }
                    }
                }
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



