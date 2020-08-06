# Failed login hook

This hook is executed as soon as a login attempt fails. It notifies the connection's IP address, login method and username. This way you can log failed attempts to an external program.

The `failed_login_hook` can be defined as the absolute path of your program or an HTTP URL.

If the hook defines an external program it can reads the following environment variables:

- `SFTPGO_LOGINFAIL_IP`
- `SFTPGO_LOGINFAIL_METHOD`
- `SFTPGO_LOGINFAIL_USERNAME`

If the hook defines an HTTP URL then this URL will be invoked as HTTP GET with the following query parameters:

- `ip`
- `method`
- `username`

The HTTP request will use the global configuration for HTTP clients.
