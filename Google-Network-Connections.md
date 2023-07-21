In general, we obviously try to minimize the connections to Google, but some services strictly rely on them and would just not work without. Blocking any network requests of microG will thus result in something not working as expected. If you don't need push notifications, you can disable it (and daily device registration) in microG settings to get rid of the corresponding network requests.

- `android.clients.google.com` is used for device registration, which is a requirement for various other services and push notifications. This happens once per day in the background if device registration is enabled.
- `android.clients.google.com` is used to register an application for push notifications. This happens when you first start an app that uses push notifications and push notifications is enabled.
- `mtalk.google.com` is the server used for push notifications. There is a persistent connection to this server when push notifications is enabled.
- `www.googleapis.com` and `android.googleapis.com` are used for DroidGuard, SafetyNet and AppCert. This happen when applications request it and device attestation is enabled.
- `www.googleapis.com` and `securetoken.googleapis.com` are used for Firebase Authentication. This happens when applications request it.
- `www.gstatic.com` and `www.google.com` are used for Firebase Authentication reCaptcha. This happens when applications request it.
- `www.googleapis.com`, `android.googleapis.com` and `accounts.google.com` are used for Google Account management. This happens when you sign in a Google Account with microG.
- `android.googleapis.com` is used for Google Account sign in. This happens when applications request it and there is a Google account signed into microG.

For all of them, we strip device identifier (MAC addresses, IMEI, etc) from requests where they normally would be (and if required use random but valid identifiers instead).