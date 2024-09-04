
# Installing InfluxDB 2.7.10 on Ubuntu

This guide will walk you through the steps to install InfluxDB 2.7.10 on an Ubuntu system.

## Step 1: Download the InfluxDB Package

First, download the InfluxDB 2.7.10 package using `wget`:

```bash
wget https://download.influxdata.com/influxdb/releases/influxdb2_2.7.10-1_amd64.deb
```

## Step 2: Install the InfluxDB Package

Once the download is complete, install the package using `dpkg`:

```bash
sudo dpkg -i influxdb2_2.7.10-1_amd64.deb
```

## Step 3: Start the InfluxDB Service

After installation, start the InfluxDB service:

```bash
sudo service influxdb start
```

## Step 4: Verify the InfluxDB Service Status

Check if the InfluxDB service is running correctly:

```bash
sudo service influxdb status
```

You should see an "active (running)" status.

<img src="">

Access the InfluxDB UI at http://localhost:8086 to complete the setup.

If the InfluxDB service is running but you cannot access the UI at http://localhost:8086, there are a few things you can check and try to resolve the issue:

## Step 5: Check Open Ports

To check which ports are open on your system, run:

```bash
ss -tulnp
```

## Step 6: Check Firewall Status

Verify the current status of your firewall:

```bash
sudo ufw status numbered
```

## Step 7: Allow InfluxDB Port in Firewall

To allow external access to InfluxDB, open port `8086` in the firewall:

```bash
sudo ufw allow 8086
```

## Additional Resources

- [InfluxDB Documentation](https://docs.influxdata.com/influxdb/latest/)
- [InfluxDB Downloads](https://portal.influxdata.com/downloads/)

By following these steps, you should have InfluxDB up and running on your Ubuntu system.