# Grafana Installation Guide

This guide provides step-by-step instructions to install Grafana on a Linux-based system.

---

## Prerequisites

Before proceeding, ensure the following:

- A Linux-based operating system (e.g., Ubuntu, CentOS).
- Root or sudo access to the system.
- wget or curl installed.
- A working internet connection.

---

## Step 1: Install Grafana

1. **Add the Grafana Repository**

   Import the Grafana GPG key:

   ```bash
   sudo apt-get install -y software-properties-common
   wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -
   ```

   Add the Grafana APT repository:

   ```bash
   echo "deb https://packages.grafana.com/oss/deb stable main" | sudo tee /etc/apt/sources.list.d/grafana.list
   ```

2. **Update Package List**

   Update the package list to include the Grafana repository:

   ```bash
   sudo apt-get update
   ```

3. **Install Grafana**

   Install Grafana using the following command:

   ```bash
   sudo apt-get install -y grafana
   ```

---

## Step 2: Start and Enable Grafana

1. **Start the Grafana Service**

   ```bash
   sudo systemctl start grafana-server
   ```

2. **Enable Grafana on Boot**

   ```bash
   sudo systemctl enable grafana-server
   ```

3. **Check Service Status**

   Verify that Grafana is running:

   ```bash
   sudo systemctl status grafana-server
   ```

---

## Step 3: Configure Firewall (Optional)

If your system has a firewall enabled, allow traffic on port 3000:

```bash
sudo ufw allow 3000/tcp
sudo ufw reload
```

---

## Step 4: Access Grafana Dashboard

1. Open a web browser.
2. Navigate to `http://<server-ip>:3000`.
3. Log in with the default credentials:
   - **Username**: `admin`
   - **Password**: `admin`
4. You will be prompted to set a new password after logging in for the first time.

---

## Step 5: Install Plugins (Optional)

You can install additional plugins using Grafana CLI. For example:

```bash
sudo grafana-cli plugins install <plugin-name>
```

Restart Grafana to apply the changes:

```bash
sudo systemctl restart grafana-server
```

---

## Step 6: Verify Installation

To ensure Grafana is running correctly:

1. Navigate to the dashboard.
2. Add a data source (e.g., Prometheus, MySQL).
3. Create a sample dashboard to visualize metrics.

---

## Conclusion

Grafana is now successfully installed and running. For advanced configurations and usage, refer to the [official Grafana documentation](https://grafana.com/docs/).
