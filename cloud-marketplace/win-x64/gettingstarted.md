# <img src="https://southrivertech.com/software/nextgen/titanmft/titanmft48.png" alt="Titan MFT logo"> Titan Managed File Transfer (MFT) for Windows</img>

Thank you for choosing Titan Managed File Transfer (MFT) - Enterprise Cloud Edition from South River Technologies. This is the Pay-as-you-go version of our solution, meaning that it will run fully featured without the need to purchase a license. Simply fire up your Titan MFT VM and run your business.

## What's on the VM?

This Titan MFT Server Virtual Machine (VM) contains a pre-built and pre-configured installation of the product. All bells and whistles are available for you to utilize and a sample server instance called Default Server has already been configured with FTP/S, SFTP, HTTP/S and WebDAV/S services enabled. There is also a test user for logging in to the system. NOTE: It is strongly recommended that you change the credentials of the test user immediately.

## Features of Titan Managed File Transfer

Titan MFT Cloud Edition is a cloud optimized version of our award winning Titan MFT Server (Managed File Transfer) deployed by on-premises customers world wide for nearly 20 years.

Titan MFT is a secure Managed File Transfer solution that allows you to automate and secure business critical file transfer workflows. A highly customizable automation engine built on open standards including an OpenAPI, SDK, CLI and others ensures the highest level connectivity with your trading partners.

Designed for the Cloud, Titan MFT takes an industry-first approach to centralized enterprise-level automated secure file transfer tasks. Native support for a wide variety of secure file transfer protocols are included for free with this edition. SFTP over SSH, Secure FTP/S, WebDAV/S for secure connectivity with SharePoint, and Enterprise File Sharing over HTTP/S using the latest TLS v1.3. Under the hood it's 2048-bit encryption technologies such as AES and PGP topped off with Keccak/SHA-3 level secure hashing options and NSA grade secure data scrubbing logic.

Our comprehensive and customizable Events Management workflow engine allows admins to discard old clunky manual processes and error prone legacy scripts. Secure file transfers and other business workflows are now fully configurable with our web-based interface allowing for a visualiztion of data flows.

Some of the features of Titan MFT which are available include:

- `Implicit FTP/S`– Implicit FTP/S is running on port 990. Connect on port 990 with your FTP client in Implicit mode and the security is immediate.
- `HTTP/S`– The secure WebUI is running on port 443 and is using a non-CA validated test certificate. While you will be able to connect on port 443, you will get warning about the invalid certificate. This it completely normal and will go away when you replace your test certificate with a valid certificate from a CA. To test, point your browser to https://localhost/ for the logon page
- `SFTP`- currently running on port 2200 and includes all strong encryption cyphers and both password and public key authentication are enabled and supported. Putty's command line PSFTP.exe utility is included in the C:\Program Files\South River Technologies\srxserver\Utils folder and can be used for testing SFTP access. Connecting to the server can be accomplished from the command line using

  > psftp -P 2200 test@localhost -pw test
  >
- `Public Host Key Authentication`- SSH's highly secure Public Key authentication has been enabled on this server. To use Public Host Key authentication, upload your SFTP client Public Key (.pub) file to the Titan MFT Server and use the Host Key Management utility to Import the client Public Key into the Titan MFT Server Admin console. Once the client's public key has been imported into the Admin console, simply locate the user's account information under the Users node and on their SFTP tab, assign the key to their account. If you have trouble with this feature, contact our help desk and we’ll be glad to help you get started
- `Email Notifications`- Titan MFT has a full Events Management system which can be leveraged to do many things, including send email notifications for alerts. To fully leverage the power of Email Notifications, please make sure to configure the settings for your specific email server under the Titan MFT Admin console's Email tab.
- `WebDAV/S` – The WebDAV protocol is enabled for collaboration. Connect to the
  Titan MFT server using any advanced WebDAV client such as WebDrive ([https://www.WebDrive.com](https://www.webdrive.com/))
  and point it to [https://Localhost:8443](https://localhost:8443/)
  for drive letter access and collaboration features.
- `PGP File Encryption` - CS supports full file encryption at rest with PGP. See the Titan MFT Admin guide included with the product for more information
  on PGP features and functionality
- Many more features are available; see the Titan MFT Admin Guide.

## Getting Started

To launch the Titan MFT Administrator UI point your browser to your VM's private url or IP address and use port 31443, e.g. https://yourdomain.com:31443 The WebUI is using a non-CA validated test certificate. While you will be able to connect, you may see a warning about the invalid certificate. This it completely normal and will go away when you replace your test certificate with a valid certificate from a CA

The first time you run the Administrator it will prompt you to create a new Administrator account to allow configuring the server.

## Configure Titan MFT for External access

The Test Server instance has been preconfigured for local access. You can access the server using the Localhost, internal IP address, or windows PC name. SFTP services are available on port 2200. Once you have performed initial testing using the internal access points and the default 'test' username, you are ready to configure the system for access from the outside.

1. Expand the Titan MFT Domains node in the tree, and then expand the Default Server Server Instance.
2. Select the Users node from the tree, click the “+” icon on the right hand side to create a new user. Follow the New User Wizard to add a new user to the system.

   > NOTE: once you create a new user, it is recommended that the test user account is disabled and/or deleted for security purposes.

3. Select the Services node located in the tree just below the Default Server node. Along the right side of the screen will be the list of services. Select "SSH/SFTP". Using the Host Key Management utility, create a new distinct host key for your new server. While Titan MFT comes pre-configured with a stock host key, this key is for testing only and should never be used in a production environment. Once you have the new key created, delete the test key.
4. Firewall Setup – Cornerstone's services are running behind both a local Firewall and the main Cloud firewall. Your cloud provider will issue a public IP address, or DNS name, for your VM. In order for Titan MFT services to function properly, Titan MFT must be configured with the External IP address of the router/firewall. This value is set on the Server Advanced tab under the Default Server node in the Titan MFT Admin Console. Replace the placeholder value with your valid IP address.

At this point, the general configurations are complete and the test user should be able to login using any industry standard SFTP, WebDAV, or FTP/S client.  Please see the Titan MFT help file for any specific settings/configuration requirements as well as how to use the new server creation wizard to generate a new, customer specific server instance.

## Notes

- `HTTP/S and FTP/S Services` – The server has been tested against both the DigiCert.com and SslLabs.com TLS security vulnerability scanner and passed. This Windows Server image has been hardened with 3DES, SHA1, TLS 1.0 and other weak ciphers being disabled.
- `FTP/S Services` - The default security mode for the data connection is PROT P. This means that if your FTP/S client does not specify PROT P or PROT C before opening a data connection, PROT P is assumed and the server will expect the client to perform a secure handshake during the transfer. Non-secure FTP, port 21, is not enabled.
- The test server has a test host key. Don't use these once you open up the server to public access as they are not meant for general use.
- The Firewall has been pre-configured to allow inbound traffic on port 2200, 990, 443, and FTP Passive range 50000-50100. This will allow external programs the ability to connect to the Titan MFT server's Default Server instance on port 2200 and via FTP and Web interface.
- SFTP services are running on port 2200. While this is not an industry standard port for SFTP, our 20+ years of experience has taught us that opening port 22 to the internet immediately invites hundreds of hackers to hammer your server trying to break in. Using a non-standard port will not only thwart hackers but also limit unnecessary traffic and bandwidth usage on your VM. We recommend moving your SFTP server to some non-standard port, such as port 2200. When you change your port in the Titan MFT Admin console on the SFTP tab, you will also need to update the SFTP port on the Windows Firewall and also in the Azure/AWS console. This will ensure that public IP traffic will be successfully routed through the Azure/AWS firewall over to your VM and your local VM's Windows Firewall will pass that same port traffic directly to your Titan MFT Server.
- If you encounter any issues, feel free to check out our help desk at http://www.SrtHelpDesk.com/ where we have many solutions guides. If you need help, please submit a ticket and use TitanMftPayg as your registration code if requested.

## Tech Support

Complimentary technical support is available on our website at https://helpdesk.titanmft.com (use TitanMftPayg as your registration code)

## WebSite(s)

South River Technologies corporate WebSite:  [https://www.southrivertech.com](https://www.southrivertech.com)<br />
Titan MFT (Enterprise grade Managed File Transfer Solution): [https://www.TitanMFT.com](https://www.TitanMFT.com)<br />
Titan DMZ Server (Secure reverse proxy server for Titan MFT): [https://www.TitanDMZ.com](https://www.TitanDMZ.com)<br />
Titan SFTP Server micro site: [https://www.TitanFTP.com](https://www.TitanFTP.com)<br />
WebDrive (Virtual Drive Mapping Client): [https://www.WebDrive.com](https://www.webdrive.com)<br />