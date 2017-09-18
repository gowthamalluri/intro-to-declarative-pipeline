# Exercise 1.1

In **Exercise 1.1** we will create a simple declarative pipeline directly within the Jenkins interface.

To create the new pipeline:

1. Log into Jenkins
2. Click on **New Item**
3. Type you name into the **Enter an item name** text box, click on **Folder**, and then click on the **OK** button.
4. Click on **Save** in the folder configuration screen to accept the default options.
5. Click on the **create new jobs** link.
6. Type **SimplePipeline** into the **Enter an item name** text box, click on **Pipeline**, and then click on the **OK** button.
7. Copy and paste the following code into the **Pipeline Script** text box:

```
pipeline {
   agent any
    
   stages {
      stage('Say Hello') {
         steps {
            echo 'Hello World!'   
         }
      }
   }
}
```
Click on **Save** and then click on **Build Now** to run your pipeline.

# Exercise 1.2

In **Exercise 1.2** we will update the pipeline we created in 1.1 to execute in a docker container. To update the pipeline:

1. Click on configure and update the ```agent``` portion of the pipeline to read:

```
   agent {
      docker { image 'maven:3.3-jdk-8' }
   }
```
