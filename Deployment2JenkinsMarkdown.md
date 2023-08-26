# Setting Up Jenkins with Python on an EC2 instance

This guide assists with setting up Jenkins on an EC2 instance, installing the "Pipeline Utility Steps" plugin for Jenkins, and setting up Python.

## 1. Install Jenkins

To install Jenkins, follow these steps:

```bash
## Update our server
sudo apt-get update

## Install Java because Jenkins needs Java to run
sudo apt install openjdk-8-jdk -y

## Install the Jenkins dependencies
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] https://pkg.jenkins.io/debian binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null

## Update our server again after new dependencies are added
sudo apt-get update

## Install the Java runtime enviornment
sudo apt-get install fontconfig openjdk-17-jre

## Install & start Jenkins
sudo apt-get install jenkins
sudo systemctl start jenkins

## Display our Jenkins admin password
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
````

## 2. Install Jenkins "Pipeline Utility Steps" Plugin
#### * WHY: This plugin will allow us to work with our zipped application files*

1. Open your Jenkins dashboard.
2. Navigate to "Manage Jenkins" from the sidebar.
3. Choose "Manage Plugins".
4. Go to the "Available" tab.
5. In the search bar, type `Pipeline Utility Steps` and hit Enter.
6. Check the box for "Pipeline Utility Steps".
7. Click on the "Install without restart" button.

## 3. Install Python
#### * WHY: We need Python installed on our machine to run our application because our application is written in Python*

To install Python on your EC2 instance, execute the following commands:

```bash
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt-get update
sudo apt-get install python3.10 python3.10-venv
python3.10 --version
````


## 4. Create a Jenkins Build
#### * WHY: This will allow is to run our Jenkins build before deploying our application to AWS Beanstalk*

### 1. **Set Up New Item**
1. Click on 'New Item'.
2. Enter the desired name for the item.
3. Select 'Pipeline' and then click 'OK'.

### 2. **Describe the Build**
1. Provide a description for your build.

### 3. **Setup the Pipeline**
1. Scroll to the 'Pipeline' section.
2. Click the menu arrow next to 'Definition' and select 'Pipeline script from SCM'.
3. In the 'SCM' dropdown, select 'Git'.

### 4. **Enter Repository Details**
1. Provide the URL of your repository in the 'Repository URL' field.

### 5. **Add Credentials**
1. Click the 'Add' button next to 'Credentials'.
2. In the 'Username' field, enter the username of your GitHub account.
3. For the 'Password' field, use your GitHub token. If you don't have one:
    Create a new GitHub token | Ensure the 'repo' and 'admin:repo_hook permissions are checked. | Click 'Generate token'. | Copy the generated token.
4. Use the copied token as the password in Jenkins.
5. For the 'ID' field, enter 'github'.
6. Provide a meaningful description.

### 6. **Finalize Build Configuration**
1. Scroll down to the 'Branches to build' section.
2. Change the branch from 'master' to 'main'.
3. Click 'Apply' and then 'Save'.

### 7. **Trigger the Build**
1. Click on 'Build Now' to initiate the build process.
