
# Running and Verification – BGPalerter

## 1. Starting BGPalerter

After completing the installation and configuration, start BGPalerter using the following command:

```bash
./bgpalerter-linux-x64
```

Make sure the binary has execution permission before running it.

```bash
chmod +x bgpalerter-linux-x64
```

## 2. Understanding the Running Process

Once BGPalerter starts, it loads the configuration file and initializes the configured connectors and monitors.

For live monitoring, BGPalerter connects to RIPE RIS Live to receive real-time BGP routing updates.

## 3. Verifying the Connection

Check the terminal output to confirm that BGPalerter has started and the RIPE RIS connector is connected.

The application should remain running while monitoring live routing updates.

## 4. Checking the Status API

BGPalerter provides a status endpoint when the REST API and uptime process monitor are configured.

Use the following command:

```bash
curl http://localhost:8011/status
```

A successful response should indicate:

- `warning: false`
- `connected: true` for the RIS connector.
- RPKI data availability.

Example successful response:

```json
{
  "warning": false,
  "connectors": [
    {
      "name": "ConnectorRIS",
      "connected": true
    }
  ],
  "rpki": {
    "data": true,
    "stale": false,
    "provider": "rpkiclient"
  }
}
```

## 5. Successful Verification

BGPalerter is successfully running when:

- The application starts without configuration errors.
- The RIPE RIS connector establishes a connection.
- The status API reports `warning: false`.
- The connector reports `connected: true`.

## 6. Conclusion

BGPalerter can be used to monitor live BGP routing updates. Its connection status can be verified through terminal output and the status API.
