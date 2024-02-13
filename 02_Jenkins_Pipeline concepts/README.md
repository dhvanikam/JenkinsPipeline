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

### References :

  https://www.jenkins.io/doc/book/pipeline/ 
