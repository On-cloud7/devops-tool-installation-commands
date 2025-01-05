# Install AWS CLI

The AWS CLI allows you to interact with AWS services from the command line.

### Steps:

1. **Download the AWS CLI installer:**
    
    ```bash
    curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
    ```
    
2. **Install unzip if not already installed:**
    
    ```bash
    sudo apt install -y unzip
    ```
    
3. **Unzip the installer:**
    
    ```bash
    unzip awscliv2.zip
    ```
    
4. **Run the installer:**
    
    ```bash
    sudo ./aws/install
    ```
    
5. **Verify the installation:**
    
    ```bash
    aws --version
    ```
    
6. **Configure AWS CLI:**
    
    ```bash
    aws configure
    ```
    
    Enter the following details:
    
    * AWS Access Key ID
        
    * AWS Secret Access Key
        
    * Default region
        
    * Default output format (e.g., JSON)
