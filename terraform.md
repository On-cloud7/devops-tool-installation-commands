# Installing Terraform

Terraform is an Infrastructure as Code (IaC) tool that lets you define and provision infrastructure using configuration files. Below are the steps to install Terraform on various operating systems.

---

## Installation on Linux

1. **Download the latest Terraform binary:**

   ```bash
   curl -LO "https://releases.hashicorp.com/terraform/$(curl -s https://releases.hashicorp.com/terraform/ | grep -o '"[0-9]\.[0-9]\.[0-9]"' | head -n 1 | tr -d '"')/terraform_$(curl -s https://releases.hashicorp.com/terraform/ | grep -o '"[0-9]\.[0-9]\.[0-9]"' | head -n 1 | tr -d '"')_linux_amd64.zip"
   ```

2. **Unzip the downloaded file:**

   ```bash
   unzip terraform_*_linux_amd64.zip
   ```

3. **Move the binary to your PATH:**

   ```bash
   sudo mv terraform /usr/local/bin/
   ```

4. **Verify the installation:**

   ```bash
   terraform version
   ```

---

## Installation on macOS

1. **Download the latest Terraform binary:**

   ```bash
   curl -LO "https://releases.hashicorp.com/terraform/$(curl -s https://releases.hashicorp.com/terraform/ | grep -o '"[0-9]\.[0-9]\.[0-9]"' | head -n 1 | tr -d '"')/terraform_$(curl -s https://releases.hashicorp.com/terraform/ | grep -o '"[0-9]\.[0-9]\.[0-9]"' | head -n 1 | tr -d '"')_darwin_amd64.zip"
   ```

2. **Unzip the downloaded file:**

   ```bash
   unzip terraform_*_darwin_amd64.zip
   ```

3. **Move the binary to your PATH:**

   ```bash
   sudo mv terraform /usr/local/bin/
   ```

4. **Verify the installation:**

   ```bash
   terraform version
   ```

---

## Installation on Windows

1. **Download the latest Terraform binary:**

   Visit the Terraform [downloads page](https://www.terraform.io/downloads) and download the Windows version.

2. **Extract the binary:**

   Use an unzip tool (e.g., WinRAR or 7-Zip) to extract the binary.

3. **Add Terraform to your PATH:**

   - Move the `terraform.exe` file to a directory in your PATH (e.g., `C:\Windows\System32`).

4. **Verify the installation:**

   ```powershell
   terraform version
   ```

---

## Managing Terraform Versions

To manage multiple Terraform versions, consider using a version manager like [tfenv](https://github.com/tfutils/tfenv).

---

For more information, refer to the official Terraform documentation: [Terraform Installation Guide](https://developer.hashicorp.com/terraform/docs/cli/install/overview).
