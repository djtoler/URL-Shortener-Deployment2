![a.png](https://github-assets-first-deployment.s3.amazonaws.com/1.1/urlshortener.PNG)

# Deployment Overview:

This is version 1.1 of the application deployment documented --> ([here](https://github.com/djtoler/firstDelpoyment/tree/main))

In version 1.1, an error is intentionally implemented into the code so that the deployment to AWS Beanstalk fails. 

# Purpose:

The purpose of our app is to transform long URLs into concise, user-friendly links. This encourages sharing and usability. We use Jenkins to enforce deployments with no errors, while AWS Beanstalk makes sure our application is always available by managing and auto-scaling our infastructure. These tools give us the potential to solve a business problem and optimize our workflow.

  #### *URL Shortener:*
  ##### URLs can be too long and not user-friendly sometimes. A URL shortener solves this by converting long URLs into shorter, more manageable URLs. This creates more user engagement because smaller URLs are more usable and more likely to be shared. Our tradeoff is that shortened URLs are associated with viruses and bad websites but users are becoming more accustomed to seeing shortened URLs and we'll get more engagement.

  #### *Jenkins:*
  ##### Manual build, test and deployment processes have more human-error and cost more time. We can use Jenkins to automate the building, testing and deployment of our application. Jenkins will reduce our risk of human-error and speed up our ability to continuiously intergrate and deploy our application. The tradeoff is that Jenkins could have a learneing curve but that investmnent of time to learn it will lower the cost of, and time to, build and deploy our app.

  #### *AWS Beanstalk:*
  ##### Managing the infrastructure for continuous application deployment can time consuming and complex. And the more complex it is, the more it will cost. AWS Beanstalk handles our applications infrastructure management. This allows us to focus on coding and implementing features while still ensuring our application will scale and be available for our users.

# Issues:
Download and look for the error in the log files to fix it, then successfully deploy the application to AWS Beanstalk.

# Steps:
## 1. [Create a new GitHub repo and download the application files from the source repo](https://github.com/djtoler/URL-Shortener-Deployment2/blob/main/Deployment2DownloadUploadFiles.md)
## 2. [Upload files to the new GitHub you created](https://github.com/djtoler/URL-Shortener-Deployment2/blob/main/UploadFilesToGitHub.md)
## 3. [Set Up Jenkins with Python on an EC2 instance & run the Jenkins Build](https://github.com/djtoler/URL-Shortener-Deployment2/blob/main/Deployment2JenkinsMarkdown.md)
## 4. [Extract the zip file that Jenkins will create](https://github.com/djtoler/URL-Shortener-Deployment2/blob/main/ExtractZipFromJenkins.md)
## 5. [Deploy the application on AWS Beanstalk](https://scribehow.com/shared/How_to_Create_and_Deploy_a_Python_URL_Shortener_on_AWS_Elastic_Beanstalk__MS9pB8lfRaGFiKAq2FU-cw) 

# System Diagram:
![a.png](https://github.com/djtoler/URL-Shortener-Deployment2/blob/main/Deployment2Diagram2.drawio.png)

# Optimization:
<aside>
✅ This deployment showed us an example of why we need to be cautious about how we're naming files and ensuring file names are consistent throught our code. Maybe we should add a test that checks and verifys file names throughout the code. Also, the problem could have been solved by changed the name used to deploy the application.

</aside>

