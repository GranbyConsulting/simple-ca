# simple-ca

Simple CA for Certificate Generation

This project contains scripts to create a basic CA and then to generate certificates
based on that authority. The certs are configured with the settings required by IPsec,
OpenVPN, or for web servers. Start by running ./mkroot and answering the questions that
are presented. This will create your CA. You can then run ./mkcert name to create a
certificate with a CN and SAN of name. The resulting certs and private keys will be
placed in the certs folder. No private key password will be applied. In order to trust
the resulting certs, the ca.crt certificate in the ca folder must be trusted by the
peer. For web severs, this means installing it as a trusted root authority on the PC,
and for tunnels, it means specifying as the remote cert source. 

If you need to creatr a wildcard certificate, you will have to provide both the wildcard
host name and the cert name as seperate arguments. ./mkcert '*.mikeg.net' mikeg will
create a certificate matching the specified pattern, storing it in files names mikeg.
