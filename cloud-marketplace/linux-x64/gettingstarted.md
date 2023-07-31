# <img src="https://srtcdnstorage.blob.core.windows.net/software/nextgen/titanmft/titanmft48.png" alt="Titan MFT logo"> Titan MFT - Enterprise Cloud Edition  for Linux</img>

Thank you for choosing Titan MFT - Cloud Edition from South River Technologies. This is the Pay-as-you-go version of our solution, meaning that it will run fully featured without the need to purchase a license from South River Technologies. Simply fire up your Titan MFT VM, and run your business.

## What's on the VM?

This Titan MFT Virtual Machine (VM) contains a pre-built and pre-configured installation of the product. 

## Features of Titan MFT

Titan MFT is a reverse proxy server that provides perimeter security for your Titan MFT implementation. Enabling you to close ports on your firewall, Titan MFT dynamically opens outbound ports to communicate with Cornerstone. User requests are sent by the Titan MFT to Titan MFT as a response on the dynamically opened channel. Working exclusively as a passthrough, no data is ever stored on or outside your firewall.

## Getting Started

Once you have securely connected to the instance over SSH, the initial Titan MFT administrator account needs to be configured. To configure the Titan MFT administrator account, use the following command and supply your new administrator credentials. It's imporant to use a complex password.

sudo /opt/southriver/titanmft/srxtitan /LASINIT /username=`<admin-username>` /password=`<admin-password>`

Once the Titan MFT administrative credentials have been established, you can now connect to the Titan MFT web-based admin console through your web-browser by pointing it to https://`<ipaddress>`:41443.

Note that this is a secure connection. However, since Titan MFT is using a temporary certificate, you will see a security warning in the browser. Proceed past the security warning and log in to the Titan MFT Admin console. At this point you will be able to configure the Titan MFT application including adding your own TLS certificate.
## Configure Titan MFT for External access

The Titan MFT instance has been preconfigured for access from an external Titan MFT server via port 45100. The public ports that Titan MFT will proxy to the Titan MFT Server will configured on your Titan MFT server but you will need to make sure the cloud provider firewall will allow those external ports through. For example, the Titan MFT server may wish for the Titan MFT to publicly listen on port 2200 for SFTP connections. In this case you will need to configure the cloud provider to allow inbound connections on port 2200 as well as the cloud provider firewall settings.

- `Port Setup` - Titan MFT services are running behind both a Windows Firewall and the main Azure/AWS firewall. Your cloud provider will issue a public IP address, or DNS name, for your VM. In order for Titan MFT services to function properly, Titan MFT must be configured with the External IP address of the router/firewall.

- `Private IP Address` - set this to the desired listening IP address where Titan MFT will connect to the Titan MFT.

- `Public IP Address` - set this to the desired public IP address issued by your cloud provider for external connections to be proxied to the Titan MFT server.

## Tech Support

Complimentary technical support is available on our website at https://helpdesk.titanmft.com (use TitanMftPAYG as your registration code)

## WebSite(s)

South River Technologies corporate WebSite:  [https://www.southrivertech.com](https://www.southrivertech.com)<br />
Titan MFT (Enterprise grade Managed File Transfer Solution): [https://www.TitanMFT.com](https://www.TitanMFT.com)<br />
Titan DMZ Server (Secure reverse proxy server for Titan MFT): [https://www.TitanDMZ.com](https://www.TitanDMZ.com)<br />
Titan SFTP Server micro site: [https://www.TitanFTP.com](https://www.TitanFTP.com)<br />
WebDrive (Virtual Drive Mapping Client): [https://www.WebDrive.com](https://www.webdrive.com)<br />
