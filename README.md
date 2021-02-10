# modernmail-middleware
A SMTP and IMAP server middleware that implements the oauth2 and multi-factor authentication specifications.

## Technical Specifications
The middleware should sit behind a gateway that passes incoming SMTP and IMAP connections
directly to the middleware. The middleware then prompts the user for the email username and password. The username and password are sent to the SMTP and IMAP server when it attempts to login. If the authentication succeeds then a 2FA prompt will be enabled. If a user has not set up a 2FA, then the user will automatically will be prompted to setup a 2FA authetnication token. The token database can be external or internal. Once the 2FA authentication is complete then a access token will be passed back to the client. And can be saved. Security policies such as token activation can be set in order to increase security base on the implemented threat model.
