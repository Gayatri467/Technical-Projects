
# Authentication and Telemetry Experiments

## 1. Overview

This project explores application authentication using ZITADEL and OpenID Connect (OIDC).

It focuses on configuring an authentication application, setting up login and redirect URLs, and testing the authentication flow for the MRT DuckDB Analytics Dashboard.

OpenTelemetry components were also explored separately to understand application observability and telemetry collection.

## 2. Project Objectives

- Understand authentication using ZITADEL.
- Configure an application in ZITADEL.
- Implement the OpenID Connect authentication flow.
- Configure login and logout redirect URLs.
- Test application login and authentication.
- Explore OpenTelemetry and distributed tracing concepts.

## 3. Technologies Used

- ZITADEL
- OpenID Connect (OIDC)
- OAuth 2.0
- OpenTelemetry
- Jaeger
- Docker
- Kubernetes

## 4. ZITADEL Setup

ZITADEL was used as the identity and access management platform.

An organization named `Duckdb-Analytics` was created, and an application named `MRT DuckDB Dashboard` was configured.

The application was configured using the Web application type with the OpenID Connect Authorization Code flow.

## 5. Application Configuration

The authentication application was configured with the following settings:

- Application type: Web
- Authentication protocol: OpenID Connect
- Grant type: Authorization Code
- Redirect URI: `http://localhost:5500/`
- Post-logout redirect URI: `http://localhost:5500/`

These URLs allow the application to handle successful login and logout redirection.

## 6. Authentication Flow

The authentication process follows these steps:

1. The user opens the dashboard.
2. The application redirects the user to ZITADEL for authentication.
3. The user enters their login credentials.
4. ZITADEL authenticates the user.
5. The user is redirected to the configured application URL.
6. The application completes the authentication flow.

## 7. Authentication Verification

The configured ZITADEL login flow was tested through the dashboard.

Successful login and redirection confirmed that the authentication configuration was working.

## 8. OpenTelemetry Experiments

OpenTelemetry was explored to understand how application telemetry can be collected and monitored.

The experiments included:

- Understanding OpenTelemetry architecture.
- Exploring telemetry collectors.
- Exploring Jaeger for distributed tracing.
- Investigating telemetry integration with the application.

The telemetry setup was later removed because it was not required for the final project implementation.

## 9. Conclusion

This project provided practical experience with application authentication using ZITADEL and OpenID Connect.

It also introduced OpenTelemetry concepts and distributed tracing tools such as Jaeger, helping build an understanding of application observability.
