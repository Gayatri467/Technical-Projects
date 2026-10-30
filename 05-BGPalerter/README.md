
# BGPalerter Monitoring

## Overview

This project focuses on setting up and configuring BGPalerter to monitor live BGP routing updates through the RIPE RIS Live streaming service.

BGPalerter receives real-time routing updates and uses monitoring modules to identify potential BGP routing issues.

The project includes configuring the RIPE RIS Live connector, monitored prefixes and ASNs, monitoring modules, and application health verification.

## Project Objectives

- Understand how BGPalerter works.
- Connect BGPalerter to RIPE RIS Live.
- Configure monitored prefixes and ASNs.
- Enable BGP monitoring modules.
- Run live BGP monitoring.
- Verify the application and connector status using the health API.

## Documentation

The following documents explain the installation, configuration, and execution process.

1. [Installation Guide](Installation.md) – Steps to download and install BGPalerter.
2. [Configuration Guide](Configuration.md) – Connector, monitor, and health API configuration.
3. [Running and Verification](Running-and-Verification.md) – Starting BGPalerter and verifying its connection status.

## Technologies Used

- BGPalerter
- RIPE RIS Live
- Linux / Ubuntu
- YAML
- REST API
- BGP (Border Gateway Protocol)

## Project Outcome

Successfully configured and ran BGPalerter with the RIPE RIS Live connector. Verified the live connector connection and application health through the status API.

## Note

This project focuses on live BGP monitoring.

