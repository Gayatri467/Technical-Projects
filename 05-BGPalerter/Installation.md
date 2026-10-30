# BGPalerter Installation Guide

## 1. Overview

BGPalerter is an open-source BGP monitoring tool that helps detect unusual routing activities, such as route hijacks and unexpected BGP path changes.

In this project, BGPalerter was installed and tested on Ubuntu Linux using its precompiled binary (version 2.0.1).

## 2. Prerequisites

Before starting, ensure the following are available:

- Ubuntu Linux or WSL Ubuntu
- Internet connection
- Terminal access
- Basic knowledge of Linux commands

## 3. Create the Working Directory

Open the Ubuntu terminal and run:

```bash
mkdir -p ~/bgpalerter-live-test
cd ~/bgpalerter-live-test
```

This creates a separate working directory for the BGPalerter live monitoring test.

## 4. Download BGPalerter

1. Open the [BGPalerter GitHub Releases](https://github.com/nttgin/BGPalerter/releases) page.
2. Download the Linux x64 binary for version 2.0.1.

Alternatively, download it using:

```bash
wget https://github.com/nttgin/BGPalerter/releases/download/v2.0.1/bgpalerter-linux-x64
```

## 5. Make the Binary Executable

Run:

```bash
chmod +x bgpalerter-linux-x64
```

This command gives the downloaded binary permission to execute.

## 6. Start BGPalerter

Run the following command:

```bash
./bgpalerter-linux-x64
```

BGPalerter starts and reads its configuration files from the working directory.

The configuration files can be created or adjusted before starting the monitoring process.

## 7. Verify the Installation

Check the terminal output for application startup and initialization messages.

Ensure that BGPalerter starts without executable or permission errors.

The RIPE RIS Live connector connection can be verified after completing the configuration steps.

## 8. Next Steps

After installation, continue with:

- Configuring the RIPE RIS Live connector.
- Adding monitored prefixes and ASNs.
- Enabling monitoring modules.
- Starting BGPalerter.
- Checking the connector connection status.
- Verifying the health API response.
