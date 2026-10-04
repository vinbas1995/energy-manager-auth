# Energy Manager OAuth client identity

Public static metadata only. This directory contains no app source, credentials, customer data or telemetry.

Home Assistant reads the `rel=redirect_uri` link to validate the native app callback `energymanager://oauth/callback`.
Client ID: https://vinbas1995.github.io/energy-manager-auth/

Authentication takes place on the user's own HTTPS Home Assistant instance. Authorization codes return directly to the Android app; this website is never a callback endpoint and receives no code or token. The application verifies a random one-use state and a ten-minute authorization timeout.

The callback uses the native custom-scheme pattern documented by Home Assistant. Home Assistant's server API does not document PKCE for this client flow; no unsupported protection is claimed. Future hardening should use a dedicated verified Android App Link domain.
