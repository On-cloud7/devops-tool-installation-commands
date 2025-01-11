# Prometheus Installation Guide

This guide will walk you through the installation and setup of Prometheus on a Linux-based system.

## Prerequisites

Before you begin, ensure that the following requirements are met:

- A Linux-based operating system (e.g., Ubuntu, CentOS).
- Root or sudo access to the system.
- wget or curl installed on the system.

---

## Step 1: Download Prometheus

1. Visit the [official Prometheus download page](https://prometheus.io/download/).
2. Alternatively, use the following command to download the latest Prometheus release:

   ```bash
   wget https://github.com/prometheus/prometheus/releases/latest/download/prometheus-{VERSION}.linux-amd64.tar.gz
   ```

   Replace `{VERSION}` with the desired version number (e.g., `2.45.0`).

---

## Step 2: Extract the Files

1. Extract the downloaded tarball:

   ```bash
   tar -xvzf prometheus-{VERSION}.linux-amd64.tar.gz
   ```

2. Navigate to the extracted directory:

   ```bash
   cd prometheus-{VERSION}.linux-amd64
   ```

---

## Step 3: Set Up Prometheus

1. Create a dedicated user for running Prometheus:

   ```bash
   sudo useradd --no-create-home --shell /bin/false prometheus
   ```

2. Create necessary directories:

   ```bash
   sudo mkdir /etc/prometheus
   sudo mkdir /var/lib/prometheus
   ```

3. Copy the configuration file and binaries:

   ```bash
   sudo cp prometheus /usr/local/bin/
   sudo cp promtool /usr/local/bin/
   sudo cp -r consoles /etc/prometheus/
   sudo cp -r console_libraries /etc/prometheus/
   sudo cp prometheus.yml /etc/prometheus/
   ```

4. Change ownership of the files and directories:

   ```bash
   sudo chown -R prometheus:prometheus /etc/prometheus
   sudo chown -R prometheus:prometheus /var/lib/prometheus
   sudo chown prometheus:prometheus /usr/local/bin/prometheus
   sudo chown prometheus:prometheus /usr/local/bin/promtool
   ```

---

## Step 4: Configure Prometheus as a Service

1. Create a systemd service file:

   ```bash
   sudo nano /etc/systemd/system/prometheus.service
   ```

   Add the following content:

   ```ini
   [Unit]
   Description=Prometheus Monitoring System
   Wants=network-online.target
   After=network-online.target

   [Service]
   User=prometheus
   Group=prometheus
   Type=simple
   ExecStart=/usr/local/bin/prometheus \
       --config.file=/etc/prometheus/prometheus.yml \
       --storage.tsdb.path=/var/lib/prometheus \
       --web.console.templates=/etc/prometheus/consoles \
       --web.console.libraries=/etc/prometheus/console_libraries

   [Install]
   WantedBy=multi-user.target
   ```

2. Reload systemd and start the service:

   ```bash
   sudo systemctl daemon-reload
   sudo systemctl start prometheus
   sudo systemctl enable prometheus
   ```

3. Check the service status:

   ```bash
   sudo systemctl status prometheus
   ```

---

## Step 5: Access the Prometheus Dashboard

1. Open a web browser.
2. Navigate to `http://<server-ip>:9090`.
3. You should see the Prometheus dashboard.

---

## Step 6: Verify the Installation

1. Run the following command to verify Prometheus is working:

   ```bash
   curl http://localhost:9090/metrics
   ```

2. Ensure the output displays Prometheus metrics.

---
