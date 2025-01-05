# Install Jenkins

### First Install JAVA on instance using :

```bash
sudo apt update
```

```bash
sudo apt install openjdk-17-jdk
```
```bash
java -version
```

### Steps:

   
1. **Add the Jenkins repository key**:
    
    ```css
    sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key

    ```
    
2. **Add Jenkins to APT sources**:
    
    ```css
    echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \https://pkg.jenkins.io/debian-stable binary/ | sudo tee \/etc/apt/sources.list.d/jenkins.list > /dev/null
    ```
    
3. **Install Jenkins**:
    
    ```css
     sudo apt-get update
     sudo apt-get install jenkins -y
    ```
    
4. **Enable Jenkins to start on boot**:
    
    ```css
     sudo systemctl enable jenkins
     sudo systemctl start jenkins
    ```
    
5. **Verify Jenkins status**:
    
    ```css
     sudo systemctl status jenkins
    ```
    
6. **Access Jenkins:** Open a browser and navigate to `http://<your-ip>:8080`. Use the password located in `/var/lib/jenkins/secrets/initialAdminPassword`.

7. **In EC2 instance add this command**:

     ```css
     sudo cat /var/lib/jenkins/secrets/initialAdminPassword
    ```



