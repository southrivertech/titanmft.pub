# <img src="https://srtcdnstorage.blob.core.windows.net/software/nextgen/titanmft/titanmft48.png" alt="Titan MFT logo"> Titan Managed File Transfer (MFT) for Linux</img>

Thank you for choosing Titan Managed File Transfer (MFT) - Cloud Edition from South River Technologies. This is the Pay-as-you-go version of our solution, meaning that it will run fully featured without the need to purchase a license. Simply fire up your Titan MFT VM and run your business.

## What's on the VM?

This Titan MFT Server Virtual Machine (VM) contains a pre-built and pre-configured installation of the product. 

## Usage Instructions / Getting Started

1) Connect securely to your vm instance over SSH using your own keypair if required.
2) Once you have securely connected to the instance over SSH, the initial Titan MFT administrator account needs to be configured. To configure the Titan MFT administrator account, use the following command and supply your new administrator credentials. It's imporant to use a complex password consisting of a minimum of 8 characters in length, both upper and lower case, one or more numbers, and one or more special characters consisting of the following characters "(~!@#$%^&*_-+=`|\\(){}[]:;\"'<>,.?/)"

```
sudo /opt/southriver/titanmft/srxtitan /LASINIT /username='<admin-username>' /password='<admin-password>'
```
3) Once the Titan MFT administrative credentials have been established, you can now connect to the Titan MFT web-based admin console through your web-browser by pointing it to https://`<ipaddress>`:47443. Note that this is a secure connection. However, since Titan MFT is using a temporary certificate, you will see a security warning in the browser. Proceed past the security warning and log in to the Titan MFT Admin console. At this point you will be able to configure the Titan MFT application including adding your own TLS certificate.


## Features of Titan Managed File Transfer

Titan MFT is a secure Managed File Transfer solution that allows you to automate and secure business critical file transfer workflows. A highly customizable automation engine built on open standards including an OpenAPI, SDK, CLI and others ensures the highest level connectivity with your trading partners.

Designed for the Cloud, Titan MFT takes an industry-first approach to centralized enterprise-level automated secure file transfer tasks. Native support for a wide variety of secure file transfer protocols are included for free with this edition. SFTP over SSH, Secure FTP/S, WebDAV/S for secure connectivity with SharePoint, and Enterprise File Sharing over HTTP/S using the latest TLS v1.3. Under the hood it's 2048-bit encryption technologies such as AES and PGP topped off with Keccak/SHA-3 level secure hashing options and NSA grade secure data scrubbing logic.

Some of the features of Titan MFT which are available include:

- `Sophisticated Scheduler`– A wide variety of scheduling options are available to automate transfer jobs to your partners.
- `PGP Encryption and Signing`– Encrypt files before sending to partners or unencrypt them when receiving from remote partners. Signature verification is also possible.
- `Connector Support`- Support for various server types including SFTP, FTP/S, Amazon S3, Google Drive and more
- `Data Loss Prevention`- With option use of Titan Neo you can use AI features to detect sensitive content before transfer, i.e. medical or financial information.
- Many more features are available; see the Titan MFT Admin Guide.

## Tech Support

Explorer suppot options at https://www.southrivertech.com/support

## WebSite(s)

South River Technologies corporate WebSite:  [https://www.southrivertech.com](https://www.southrivertech.com)<br />
Titan MFT (Enterprise grade Managed File Transfer Solution): [https://www.TitanMFT.com](https://www.TitanMFT.com)<br />
Titan DMZ Server (Secure reverse proxy server for Titan MFT): [https://www.TitanDMZ.com](https://www.TitanDMZ.com)<br />
Titan SFTP Server micro site: [https://www.TitanFTP.com](https://www.TitanFTP.com)<br />
WebDrive (Virtual Drive Mapping Client): [https://www.WebDrive.com](https://www.webdrive.com)<br />
