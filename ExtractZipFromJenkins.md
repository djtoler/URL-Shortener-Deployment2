# How to Extract The New Application Zip File From Your Jenkins Output & Use It In Your AWS Beanstalk Deployment

## Setting up Git and Pushing Our Application Zip File to GitHub from Our EC2

1. **Check Git Version**: This will let you know if Git is installed and its version. If its not installed, install it.
    ```bash
    git --version
    ```

2. **Set Global Git Configuration**:
    ```bash
    git config --global user.name "your_GitHub_username"
    git config --global user.email "the_email_associated_with_your_GitHub"
    ```

3. **Clone the GitHub Repository**:
    ```bash
    git clone https://github.com/djtoler/URL-Shortener-Deployment2
    ```

4. **Navigate to Jenkins Build Directory**:
    ```bash
    cd /var/lib/jenkins/workspace/Deployment2JenkinsBuild/build/
    ls
    ```

5. **Copy the zip file to the Cloned GitHub Directory**:
    ```bash
    cp 1.0.0.1.zip /home/ubuntu/URL-Shortener-Deployment2/
    ```

6. **Navigate to the Cloned GitHub Directory and List Files**:
    ```bash
    cd /home/ubuntu/URL-Shortener-Deployment2/
    ls
    ```

7. **Add Changes, Commit, and Push to GitHub**:
    ```bash
    git add .
    git commit -m"added zip file 1.0.0.1"
    git push
    ```

## Setting up Git and Pulling Our Application Zip File from GitHub to Our Local Machine

1. **Check Git Version**: This will let you know if Git is installed and its version. If its not installed, install it.
    ```bash
    git --version
    ```

2. **Set Global Git Configuration**:
    ```bash
    git config --global user.name "your_GitHub_username"
    git config --global user.email "the_email_associated_with_your_GitHub"
    ```

3. **Clone the GitHub Repository**:
    ```bash
    git clone https://github.com/djtoler/URL-Shortener-Deployment2
    ```
