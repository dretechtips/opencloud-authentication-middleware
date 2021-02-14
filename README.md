# opencloud authentication middleware
A universal external authentication module for any self-hosted services. This software follows the [suckless](https://suckless.org) philosphy for the web. In practice this means the built-in frontend includes zero client side code execution and no css code to ensure a minimalist online authentication middleware. The server side only does the bare minimium of handling the transport and application layer active connections. Application layer authentication will be handled by application plugins. All services authentication will be handled modularly through scripts and service config files.

## Features
* oAuth2 Style Authentication
* 2FA Authentication
* Modular Service Management that works on the level 4 or level 7 layer.

## Technical Specifications

### Transport Layer

The middleware should sit behind a gateway that passes incoming protocol connections directly to the middleware. The middleware then prompts the user for the email username and password. The username and password are sent to the protocol server where it attempts an authentication. If the authentication succeeds then a 2FA prompt will be enabled. If a user has not set up a 2FA, then the user will automatically will be prompted to setup a 2FA authentication token. The token database can be external or internal. Once the 2FA authentication is complete then a access token will be passed back to the client and a proxy connection will be established. The client will be able to access the tunnel proxy connection with the client token. Security policies such as token activation time and geo-location restriction[based off IP range] can be set in order to increase security based on the implemented threat model.

### Prebuilt Application Layer

* [HTTP/S](https://github.com/saandre15/opencloud-auth-http-plugin)
