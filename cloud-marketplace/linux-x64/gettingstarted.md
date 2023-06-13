# `<img src="https://southrivertech.com/software/nextgen/cornerstone/cornerstone48.png" alt="Cornerstone MFT logo">` Cornerstone MFT - Enterprise Cloud Edition  for Linux`</img>`

Thank you for choosing Cornerstone MFT - Cloud Edition from South River Technologies. This is the Pay-as-you-go version of our solution, meaning that it will run fully featured without the need to purchase a license from South River Technologies. Simply fire up your Cornerstone MFT VM, and run your business.

## What's on the VM?

This Cornerstone MFT Virtual Machine (VM) contains a pre-built and pre-configured installation of the product.

## Features of Cornerstone MFT

Cornerstone is a reverse proxy server that provides perimeter security for your Cornerstone implementation. Enabling you to close ports on your firewall, Cornerstone dynamically opens outbound ports to communicate with Cornerstone. User requests are sent by the Cornerstone MFT to Cornerstone as a response on the dynamically opened channel. Working exclusively as a passthrough, no data is ever stored on or outside your firewall.

## Getting Started

Once you have securely connected to the instance over SSH, the initial Cornerstone administrator account needs to be configured. To configure the Cornerstoneadministrator account, use the following command and supply your new administrator credentials. It's imporant to use a complex password.

sudo /opt/southriver/srxserver/srxserver /LASINIT /username=`<admin-username>` /password=`<admin-password>`

Once the Cornerstoneadministrative credentials have been established, you can now connect to the Cornerstoneweb-based admin console through your web-browser by pointing it to https://`<ipaddress>`:41443.

Note that this is a secure connection. However, since Cornerstoneis using a temporary certificate, you will see a security warning in the browser. Proceed past the security warning and log in to the CornerstoneAdmin console. At this point you will be able to configure the Cornerstone application including adding your own TLS certificate.

## Configure Cornerstone for External access

The Cornerstone MFT instance has been preconfigured for access from an external Cornerstone server via port 45100. The public ports that Cornerstone will proxy to the Cornerstone Server will configured on your Cornerstone server but you will need to make sure the cloud provider firewall will allow those external ports through. For example, the Cornerstone server may wish for the Cornerstone MFT to publicly listen on port 2200 for SFTP connections. In this case you will need to configure the cloud provider to allow inbound connections on port 2200 as well as the cloud provider firewall settings.

- `Port Setup` - Cornerstone services are running behind both a Windows Firewall and the main Azure/AWS firewall. Your cloud provider will issue a public IP address, or DNS name, for your VM. In order for Cornerstone services to function properly, Cornerstone must be configured with the External IP address of the router/firewall.
- `Private IP Address` - set this to the desired listening IP address where Cornerstone will connect to the Cornerstone MFT.
- `Public IP Address` - set this to the desired public IP address issued by your cloud provider for external connections to be proxied to the Cornerstone server.

## Tech Support

Complimentary technical support is available on our website at https://helpdesk.cornerstonemft.com (use CornerstonePAYG as your registration code)

## WebSite(s)

South River Technologies corporate WebSite:  [https://www.SouthRiverTechnologies.com](https://www.SouthRiverTechnologies.com)`<br />`
Cornerstone MFT (Enterprise grade Managed File Transfer Solution): [https://www.CornerstoneMFT.com](https://www.cornerstonemft.com)`<br />`
DMZedge Server (Secure reverse proxy server for Cornerstone MFT): [https://www.dmzedge.com](https://www.dmzedge.com)`<br />`
Titan SFTP Server micro site: [https://www.titanftp.com](https://www.titanftp.com)`<br />`
WebDrive (Virtual Drive Mapping Client): [https://www.WebDrive.com](https://www.webdrive.com)`<br />`
