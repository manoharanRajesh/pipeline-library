# pipeline-library
Jenkins shared library for use with pipeline-as-code. You can use (parts of) this library in you `Jenkinsfile`.


 [pipeline-examples](https://github.com/jenkinsci/pipeline-examples)
How to use
----------
* Fork this repo.
* Modify the `Constants.groovy` file and supply your specific configuration parameters (e.g. GitLab url, SonarQube url).
* Add your forked git repo to your Jenkins instance: *Manage Jenkins > Configure System > Global Pipeline Libraries* and name it `pipeline-library`.
* Import the global shared library into your `Jenkinsfile`:
    ```
    @Library('pipeline-library')
    import politie.jenkins.*

    def builder = new JenkinsPipelineBootstrap().createBuilder()

    String serviceName = 'my-service'
    String gitBranch = 'master'

    builder.mavenApplicationPipeline(serviceName, gitBranch)        
    ```
* Start your Jenkins job.

Note: if you just want to take advantage of our custom step definitions, take a look at [JenkinsPipelineSteps.groovy](src/politie/jenkins/JenkinsPipelineSteps.groovy)

Contributors
----------

* [Bert Jan](https://github.com/bertjan)
* [Arno](https://github.com/arnobroekhof)
* [Richard](https://github.com/rkettelerij)
