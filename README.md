# opencloud authentication middleware
Opencloud oauth2 and multi-factor authentication that is compatible with service standards.

## Email Technical Specifications
The middleware should sit behind a gateway that passes incoming SMTP and IMAP connections
directly to the middleware. The middleware then prompts the user for the email username and password. The username and password are sent to the SMTP and IMAP server when it attempts to login. If the authentication succeeds then a 2FA prompt will be enabled. If a user has not set up a 2FA, then the user will automatically will be prompted to setup a 2FA authetnication token. The token database can be external or internal. Once the 2FA authentication is complete then a access token will be passed back to the client and a proxy connection will be established. The client will be able to access the SMTP and IMAP proxy connection with the client token. Security policies such as token activation time and geo-location restriction[based off IP range] can be set in order to increase security base on the implemented threat model.
