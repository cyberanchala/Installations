
# Installing Grafana 11.2.0 on Ubuntu

This guide covers the steps to install Grafana 11.2.0, the latest OSS version, on an Ubuntu system.

## 1. Update the System

First, ensure that your package list is up-to-date:

```bash
sudo apt-get update
sudo apt-get upgrade
```

## 2. Install Required Dependencies

Grafana requires some dependencies like `adduser`,  `libfontconfig` and `musl`. Install them with the following command:

```bash
sudo apt-get install -y adduser libfontconfig1 musl
```

## 3. Download the Grafana 11.2.0 .deb Package

Download the Grafana 11.2.0 package from the official Grafana website or use `wget`:

```bash
wget https://dl.grafana.com/oss/release/grafana_11.2.0_amd64.deb
```

## 4. Install Grafana

Use `dpkg` to install the downloaded .deb package:

```bash
sudo dpkg -i grafana_11.2.0_amd64.deb
```

If there are any dependency issues, resolve them with:

```bash
sudo apt-get install -f
```

## 5. Start and Enable Grafana Service

After installing Grafana, start the Grafana service and enable it to start on boot:

```bash
sudo systemctl start grafana-server
sudo systemctl enable grafana-server
```

## 6. Verify the Installation

Check if Grafana is running correctly:

```bash
sudo systemctl status grafana-server
```

You should see an "active (running)" status.

<img src= "https://github.com/cyberanchala/Installations/blob/main/grafana-active-status.png">

## 7. Access Grafana

Grafana should now be accessible via your web browser at `http://localhost:3000`. The default login credentials are:

- **Username:** `admin`
- **Password:** `admin`

You will be prompted to change the password upon first login.

## 8. (Optional) Configure Firewall

If you need to access Grafana remotely, ensure that port `3000` is open:

```bash
sudo ufw allow 3000/tcp
```

## 9. (Optional) Install Plugins

If you plan to use any Grafana plugins, you can install them using the Grafana CLI:

```bash
sudo grafana-cli plugins install <plugin-name>
```

## 10. (Optional) Secure Grafana

Consider securing your Grafana installation by configuring HTTPS and setting up user authentication.

## Resources

- [Grafana Installation Documentation](https://grafana.com/docs/grafana/latest/setup-grafana/installation/debian/)
- [Grafana Download Page](https://grafana.com/grafana/download)

