# Installing kubectl

`kubectl` is the Kubernetes command-line tool that allows you to interact with Kubernetes clusters. Below are the steps to install `kubectl` on various operating systems.

---

## Installation on Linux

1. **Download the latest version of kubectl:**

   ```bash
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
   ```

2. **Make the binary executable:**

   ```bash
   chmod +x kubectl
   ```

3. **Move the binary to your PATH:**

   ```bash
   sudo mv kubectl /usr/local/bin/
   ```

4. **Verify the installation:**

   ```bash
   kubectl version --client
   ```

---

## Installation on macOS

1. **Download the latest version of kubectl:**

   ```bash
   curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/darwin/amd64/kubectl"
   ```

2. **Make the binary executable:**

   ```bash
   chmod +x kubectl
   ```

3. **Move the binary to your PATH:**

   ```bash
   sudo mv kubectl /usr/local/bin/
   ```

4. **Verify the installation:**

   ```bash
   kubectl version --client
   ```

---

## Installation on Windows

1. **Download the latest version of kubectl:**

   Use PowerShell to download the binary:

   ```powershell
   curl.exe -LO "https://dl.k8s.io/release/$(curl.exe -L -s https://dl.k8s.io/release/stable.txt)/bin/windows/amd64/kubectl.exe"
   ```

2. **Add the binary to your PATH:**

   - Move `kubectl.exe` to a directory in your system's PATH (e.g., `C:\Windows\System32`).

3. **Verify the installation:**

   ```powershell
   kubectl version --client
   ```

---

## Additional Setup (Optional)

### Enable Shell Autocompletion

1. **For bash:**

   ```bash
   source <(kubectl completion bash)
   echo "source <(kubectl completion bash)" >> ~/.bashrc
   ```

2. **For zsh:**

   ```bash
   source <(kubectl completion zsh)
   echo "source <(kubectl completion zsh)" >> ~/.zshrc
   ```

---

For more information, refer to the official Kubernetes documentation: [kubectl Installation Guide](https://kubernetes.io/docs/tasks/tools/).
