# Jenkins Pipeline Basic Concepts

## What is Jenkins Pipeline?
Jenkins Pipeline is a suite of plugins which supports implementing and integrating continuous delivery pipelines into Jenkins.

A continuous delivery (CD) pipeline is an automated expression of your process for getting software from version control right through to your users and customers. Every change to your software (committed in source control) goes through a complex process on its way to being released. This process involves building the software in a reliable and repeatable manner, as well as progressing the built software (called a "build") through multiple stages of testing and deployment.

## Jenkins Freestyle Project 

Use GUI to add different stages and steps.

More suitable for less complex scenarios.

Good when you are starting to use Jenkins/ CI solutions.

It can become hard to achieve complex scenario.


## Why Pipeline over FreeStyle Project?
Pipeline adds a powerful set of automation tools onto Jenkins, supporting use cases that span from simple continuous integration to comprehensive CD pipelines. By modeling a series of related tasks, users can take advantage of the many features of Pipeline:

1. **Code**: Pipelines are implemented in code and typically checked into source control, giving teams the ability to edit, review, and iterate upon their delivery pipeline.

2. **Durable**: Pipelines can survive both planned and unplanned restarts of the Jenkins controller.

3. **Pausable**: Pipelines can optionally stop and wait for human input or approval before continuing the Pipeline run.

4. **Versatile**: Pipelines support complex real-world CD requirements, including the ability to fork/join, loop, and perform work in parallel.

5. **Extensible**: The Pipeline plugin supports custom extensions to its DSL and multiple options for integration with other plugins.

## Example Pipeline Flow

There many steps involved in Build and Deploy stages but for now We will be more focus on Test stage of the pipeline

![Pipeline drawio](https://github.com/dhvanikam/JenkinsPipeline/assets/73573915/1616f521-4de1-4313-a2f1-26f0d97e3d09)


## Declarative versus Scripted Pipeline syntax
A Jenkinsfile can be written using two types of syntax — Declarative and Scripted.
Declarative and Scripted Pipelines are constructed fundamentally differently. Declarative Pipeline is a more recent feature of Jenkins Pipeline which:

* provides richer syntactical features over Scripted Pipeline syntax, and
* is designed to make writing and reading Pipeline code easier.

We will focus on declaritive syntax only.

For more information :

https://www.jenkins.io/doc/book/pipeline/#scripted-pipeline-fundamentals

https://www.jenkins.io/doc/book/pipeline/#declarative-pipeline-fundamentals

## Pipeline concepts
The following concepts are key aspects of Jenkins Pipeline, which tie in closely to Pipeline syntax (see the overview below).

#### Pipeline
A Pipeline is a user-defined model of a CD pipeline. A Pipeline’s code defines your entire build process, which typically includes stages for building an application, testing it and then delivering it.
Also, a pipeline block is a key part of Declarative Pipeline syntax.
```
pipeline {
.....
....
}
```

#### Stage
A stage block defines a conceptually distinct subset of tasks performed through the entire Pipeline (e.g. "Build", "Test" and "Deploy" stages), which is used by many plugins to visualize or present Jenkins Pipeline status/progress.

```
pipeline {
   agent any
   stages {
     stage('Build'){
      ....
     }
   }
}
```
#### Step
A single task. Fundamentally, a step tells Jenkins what to do at a particular point in time (or "step" in the process). For example, to execute the shell command make, use the sh step: sh 'make'. When a plugin extends the Pipeline DSL, that typically means the plugin has implemented a new step.
```
pipeline {
   agent any
   stages {
     stage('Build'){
       steps {
            ....
          }
       }
   }
}
```
#### Example basic pipeline
```
pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                //
            }
        }
        stage('Test') {
            steps {
                //
            }
        }
        stage('Deploy') {
            steps {
                //
            }
        }
    }
}
```
### References :
  
  https://www.jenkins.io/doc/book/pipeline/ 
