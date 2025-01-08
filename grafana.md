
# Grafana Installation Guide

This guide will walk you through the installation of Grafana on your system.

## Prerequisites

- A Linux, macOS, or Windows machine
- Administrative or sudo privileges for installation
- Internet access to download necessary packages

## Installation Steps

### 1. Install Grafana on Linux

#### Using APT (Debian/Ubuntu)

1. **Install dependencies:**

   ```bash
   sudo apt-get install -y software-properties-common
   ```

2. **Add the Grafana APT repository:**

   ```bash
   sudo add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"
   ```

3. **Import the Grafana GPG key:**

   ```bash
   sudo apt-get install -y gnupg2
   curl https://packages.grafana.com/gpg.key | sudo apt-key add -
   ```

4. **Update your package list:**

   ```bash
   sudo apt-get update
   ```

5. **Install Grafana:**

   ```bash
   sudo apt-get install grafana
   ```

6. **Start and enable Grafana:**

   ```bash
   sudo systemctl start grafana-server
   sudo systemctl enable grafana-server
   ```

7. **Access Grafana:**

   Open your browser and go to `http://localhost:3000`. The default login credentials are:

   - **Username:** admin
   - **Password:** admin (you will be prompted to change it)

### 2. Install Grafana on macOS

#### Using Homebrew

1. **Install Homebrew** (if you don't have it already):

   Visit [Homebrew's official site](https://brew.sh) for installation instructions or run:

   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Install Grafana:**

   ```bash
   brew install grafana
   ```

3. **Start Grafana:**

   ```bash
   brew services start grafana
   ```

4. **Access Grafana:**

   Open your browser and go to `http://localhost:3000`. The default login credentials are:

   - **Username:** admin
   - **Password:** admin (you will be prompted to change it)

### 3. Install Grafana on Windows

#### Using Chocolatey

1. **Install Chocolatey** (if you don't have it already):

   Follow the instructions on [Chocolatey's official website](https://chocolatey.org/install).

2. **Install Grafana:**

   ```powershell
   choco install grafana
   ```

3. **Start Grafana:**

   You can start Grafana from the Start Menu, or using the following command:

   ```powershell
   Start-Service grafana
   ```

4. **Access Grafana:**

   Open your browser and go to `http://localhost:3000`. The default login credentials are:

   - **Username:** admin
   - **Password:** admin (you will be prompted to change it)

### 4. Verify Installation

After accessing the Grafana UI:

- Check the server status at the top of the screen.
- Set up data sources by navigating to **Configuration → Data Sources**.
- Start creating dashboards by selecting **+** → **Dashboard**.

## Additional Configuration

To change the default port or modify other configurations, you can edit the Grafana configuration file:

- **Linux/macOS:** `/etc/grafana/grafana.ini`
- **Windows:** `C:\Program Files\GrafanaLabs\grafana\conf\defaults.ini`

### Stopping and Restarting Grafana

To stop or restart Grafana, use the following commands:

- **Linux:**

   ```bash
   sudo systemctl stop grafana-server
   sudo systemctl restart grafana-server
   ```

- **macOS (Homebrew):**

   ```bash
   brew services stop grafana
   brew services restart grafana
   ```

- **Windows:**

   ```powershell
   Stop-Service grafana
   Restart-Service grafana
   ```

## Troubleshooting

- **Grafana Not Starting:**
   - Check the logs at `/var/log/grafana/grafana.log` (Linux) or the event viewer (Windows).
   - Ensure that the necessary ports are open and not being used by other services.

## Uninstalling Grafana

To uninstall Grafana, follow the steps below:

- **Linux (APT):**

   ```bash
   sudo apt-get remove --purge grafana
   ```

- **macOS (Homebrew):**

   ```bash
   brew uninstall grafana
   ```

- **Windows (Chocolatey):**

   ```powershell
   choco uninstall grafana
   ```
