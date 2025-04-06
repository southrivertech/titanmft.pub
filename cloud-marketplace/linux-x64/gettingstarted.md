# <img src="https://srtcdnstorage.blob.core.windows.net/software/nextgen/titanmft/titanmft48.png" alt="Titan MFT logo"> Titan Managed File Transfer (MFT) for Linux</img>

Thank you for choosing Titan Managed File Transfer (MFT) - Enterprise Cloud Edition from South River Technologies. This is the Pay-as-you-go version of our solution, meaning that it will run fully featured without the need to purchase a license. Simply fire up your Titan MFT VM and run your business.

## What's on the VM?

This Titan MFT Server Virtual Machine (VM) contains a pre-built and pre-configured installation of the product. All bells and whistles are available for you to utilize and a sample server instance called Default Server has already been configured with FTP/S, SFTP, HTTP/S and WebDAV/S services enabled. There is also a test user for logging in to the system however the user account is disabled by default so you will need to edit the user and enable the account before you can login. NOTE: It is strongly recommended that you change the credentials of the test user immediately.

## Usage Instructions / Getting Started

1) Connect securely to your vm instance over SSH using your own keypair.
2) Once you have securely connected to the instance over SSH, the initial Titan MFT administrator account needs to be configured. To configure the Titan MFT administrator account, use the following command and supply your new administrator credentials. It's imporant to use a complex password consisting of a minimum of 8 characters in length, both upper and lower case, one or more numbers, and one or more special characters consisting of the following characters "(~!@#$%^&*_-+=`|\\(){}[]:;\"'<>,.?/)"

```
sudo /opt/southriver/titanmft/srxtitan /LASINIT /username='<admin-username>' /password='<admin-password>'
```
3) After the password hase been created you can hit control-c to return to the shell.
4) Once the Titan MFT administrative credentials have been established, you can now connect to the Titan MFT web-based admin console through your web-browser by pointing it to https://`<ipaddress>`:41443. Note that this is a secure connection. However, since Titan MFT is using a temporary certificate, you will see a security warning in the browser. Proceed past the security warning and log in to the Titan MFT Admin console. At this point you will be able to configure the Titan MFT application including adding your own TLS certificate.


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

## Notes

- `HTTP/S and FTP/S Services` – The server has been tested against both the DigiCert.com and SslLabs.com TLS security vulnerability scanner and passed. This Windows Server image has been hardened with 3DES, SHA1, TLS 1.0 and other weak ciphers being disabled.
- `FTP/S Services` - The default security mode for the data connection is PROT P. This means that if your FTP/S client does not specify PROT P or PROT C before opening a data connection, PROT P is assumed and the server will expect the client to perform a secure handshake during the transfer. Non-secure FTP, port 21, is not enabled.
- The test server has a test host key. Don't use these once you open up the server to public access as they are not meant for general use.
- The Firewall has been pre-configured to allow inbound traffic on port 2200, 990, 443, and FTP Passive range 50000-50100. This will allow external programs the ability to connect to the Titan MFT server's Default Server instance on port 2200 and via FTP and Web interface.
- SFTP services are running on port 2200. While this is not an industry standard port for SFTP, our 20+ years of experience has taught us that opening port 22 to the internet immediately invites hundreds of hackers to hammer your server trying to break in. Using a non-standard port will not only thwart hackers but also limit unnecessary traffic and bandwidth usage on your VM. We recommend moving your SFTP server to some non-standard port, such as port 2200. When you change your port in the Titan MFT Admin console on the SFTP tab, you will also need to update the SFTP port on the Windows Firewall and also in the Azure/AWS console. This will ensure that public IP traffic will be successfully routed through the Azure/AWS firewall over to your VM and your local VM's Windows Firewall will pass that same port traffic directly to your Titan MFT Server.
- If you encounter any issues, feel free to check out our help desk at http://www.SrtHelpDesk.com/ where we have many solutions guides. If you need help, please submit a ticket and use TitanMftPayg as your registration code if requested.

## Tech Support

Complimentary technical support is available on our website at https://helpdesk.titanmft.com (use TitanMftPAYG as your registration code)

## WebSite(s)

South River Technologies corporate WebSite:  [https://www.southrivertech.com](https://www.southrivertech.com)<br />
Titan MFT (Enterprise grade Managed File Transfer Solution): [https://www.TitanMFT.com](https://www.TitanMFT.com)<br />
Titan DMZ Server (Secure reverse proxy server for Titan MFT): [https://www.TitanDMZ.com](https://www.TitanDMZ.com)<br />
Titan SFTP Server micro site: [https://www.TitanFTP.com](https://www.TitanFTP.com)<br />
WebDrive (Virtual Drive Mapping Client): [https://www.WebDrive.com](https://www.webdrive.com)<br />
