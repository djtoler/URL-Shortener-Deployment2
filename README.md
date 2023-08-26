![a.png](https://github-assets-first-deployment.s3.amazonaws.com/1.1/urlshortener.PNG)

# Deployment Overview:

This is version 1.1 of the application deployment documented --> ([here](https://github.com/djtoler/firstDelpoyment/tree/main))

In version 1.1, an error is intentionally implemented into the code so that the deployment to AWS Beanstalk fails. 

# Purpose:

The application passed the build and test phases in Jenkins but will not successfully deploy to AWS Beanstalk because of the intentional error. The objective is to find the error, fix the error and successfully deploy the application to AWS Beanstalk.

# Issues:
Download and look for the error in the log files to fix it, then successfully deploy the application to AWS Beanstalk.

# Steps:
## 2. [Setting Up Jenkins with Python on an EC2 instance](https://github.com/djtoler/URL-Shortener-Deployment2/blob/main/Deployment2JenkinsMarkdown.md)

# System Diagram:

# Takeaways:
<aside>
✅ This deployment showed us an example of why we need to be cautious about how we're naming files and ensuring file names are consistent throught our code. Maybe we should add a test that checks and verifys file names throughout the code. Also, the problem could have been solved by changed the name used to deploy the application.

</aside>

