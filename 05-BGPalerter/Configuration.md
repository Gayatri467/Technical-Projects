# BGPalerter Configuration Guide

## 1. Overview

BGPalerter uses configuration files to connect to BGP data sources, monitor routing information, and detect possible routing anomalies.

This guide explains the main configuration sections used in the live BGP monitoring setup.

## 2. Main Configuration File

The main configuration file is named `config.yml`.

It contains the application version, environment, connectors, monitoring modules, and process monitors.

## 3. Configure the RIPE RIS Live Connector

The RIPE RIS Live connector receives live BGP routing updates.

Example configuration:

```yaml
configVersion: 3
environment: production

connectors:
  - file: connectorRIS
    name: ris
    params:
      carefulSubscription: true
      url: ws://ris-live.ripe.net/v1/ws/
      perMessageDeflate: true
      subscription:
        moreSpecific: true
        type: UPDATE
        host: null
        socketOptions:
          includeRaw: false
```

**Important settings:**

- `connectorRIS`: Selects the RIPE RIS Live connector.
- `url`: Specifies the RIPE RIS Live WebSocket endpoint.
- `type: UPDATE`: Subscribes to BGP update messages.
- `moreSpecific: true`: Includes more-specific prefixes in the subscription.
- `carefulSubscription: true`: Enables careful subscription handling.

## 4. Configure Monitoring Modules

Monitoring modules analyse incoming BGP routing information.

The live test used the following modules:

```yaml
monitors:
  - file: basic-hijack-detection
    params:
      thresholdMinPeers: 3

  - file: path
```

- `basic-hijack-detection`: Checks for possible route hijacking based on configured monitoring conditions.
- `thresholdMinPeers`: Sets the minimum peer threshold used by the hijack detection monitor.
- `path`: Monitors BGP AS path information.

## 5. Configure Monitored Prefixes

The `prefixes.yml` file defines the IP prefixes and expected AS numbers to monitor.

Example:

```yaml
193.0.10.0/23:
  description: BGP monitoring test prefix
  asn:
    - 64496
  ignoreMorespecifics: false
  ignore: false
  group: test
```

**Important:** The prefix and ASN above are an example from the test configuration. Use prefixes and ASNs that you are authorized to monitor.

## 6. Configure the Health API

The live test enabled the `uptimeApi` process monitor in `config.yml`:

```yaml
processMonitors:
  - file: uptimeApi
    params:
      useStatusCodes: true
```

The health API was configured to listen on port `8011`.

It provides a status endpoint that can be used to check the BGPalerter process and connector status.

## 7. Configuration Summary

| File or section | Purpose |
|---|---|
| `config.yml` | Main application configuration |
| `connectorRIS` | Receives live BGP updates |
| `monitors` | Defines routing monitoring modules |
| `prefixes.yml` | Defines monitored prefixes and ASNs |
| `processMonitors` | Enables process health monitoring |

## 8. Next Step

After configuring the files, start BGPalerter and verify that the RIPE RIS Live connector is connected.
