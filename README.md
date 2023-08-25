![a.png](https://github-assets-first-deployment.s3.amazonaws.com/1.1/urlshortener.PNG)

# Deployment Overview:

This is version 1.1 of the application deployment documented --> ([here](https://github.com/djtoler/firstDelpoyment/tree/main))

In version 1.1, an error is intentionally implemented into the code so that the deployment to AWS Beanstalk fails. 

# Problem Statement:

The application passed the build and test phases in Jenkins but will not successfully deploy to AWS Beanstalk because of the intentional error. The objective is to find the error, fix the error and successfully deploy the application to AWS Beanstalk.

# Solution:
Download and look for the error in the log files to fix it, then successfully deploy the application to AWS Beanstalk.

# Results:
 After reviewing the log files, an error message labeled "ModuleNotFoundError: No module named 'application'" was found. 
![aaa.png](https://github-assets-first-deployment.s3.amazonaws.com/1.1/1.1deploymentlogswitharrow.PNG)

## This means that in order to deploy successfully, theres supposed to be a module named "application" but we dont have one. We have 'app', so we should change the file name to application.py

| Before                              | After                               |
| ----------------------------------- | ----------------------------------- |
| ![aaaaaa.png](https://github-assets-first-deployment.s3.amazonaws.com/1.1/1.1applicationfile.PNG) | ![aaaaaa.png](https://github-assets-first-deployment.s3.amazonaws.com/1.1/1.1appfile.PNG) |


## I changed the name of the file using the following command

```bash
mv app.py application.py
```


## This rusulted in a successful application deployment to AWS Beanstalk.
![aaaaa.png](https://github-assets-first-deployment.s3.amazonaws.com/1.1/1.1BeanstalkBuuildSuccess.PNG) <br><br>

# Takeaways:
<aside>
✅ This deployment showed us an example of why we need to be cautious about how we're naming files and ensuring file names are consistent throught our code. Maybe we should add a test that checks and verifys file names throughout the code. Also, the problem could have been solved by changed the name used to deploy the application.

</aside>

