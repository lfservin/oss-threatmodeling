# Quick and dirty list of vulnerabilities

## Inconsistencies

1. Customer swipes the card and the kiosk sends the information via the REST api to the admin service which calls the payment service ( See D1 for details )

    The detail image has no such flow, but on to the order service flow (number 6) it states:

    The Kiosk communicates order and payment information to the order services to process the order.

2. Unencrypted comm to the order service from the printers, but port 80 is not open on the firewall. So, no printing?

3. Payment service and DB. High level description (D1): [...] payment service then writes the payment token to the database and releases the order for delivery to the food prep staff
There is no such dataflow in the detailed description. So that must be taken care of by the order service as well.

## Findings

Some of the findings are pretty obvious, some not so much. Here is a list of vulnerabilities on a quick pass. The idea of the workshop is to come up with as many as possible together with the audience, so I'm more concentrated on the modeling side for the preparation.

* unencrypted communications: printer to order service, payment and order services
* insufficient authentication: Printer uses GUIDs as authentication method, admin portal only uses username/pwd (no info on whether there are any checks on attempts per ip, blocking of account for failed attempts, etc)
* Insufficient privilege (authorization) checks: printer to order service; kiosk to admin service (how is the certificate identity (layer4) translated into access to admin portal (layer 7)?); order to payment service (unauthenticated)
* Shared credentials for infrastructure access
* Credentials stored in clear text: jump host to all servers, order service to db, certificate keys in the kiosk
* hard-coded credentials: admin service
* insufficient resiliency of infrastructure: No information as to how it is hosted (server types, patching, backups, DR plans, etc)
* self-designed cryptography: order service
* possible injection: kiosk allows free-form text: how is it validated/ sanitized to hinder XSS/SQLi, etc? Possibly Angular catches many of these things, but code detail would be needed
* Certificate lifecycle:  How are kiosk certificates managed? What does the PKI infrastructure look like? CRLs? Rotation after x years?
* Upgrades with unchecked binaries: Are signed binaries used? Are signatures checked before flashing?
* DHCP / DNS for kiosks: if this are coming from the customer network can they be trusted? Potential vector for redirecting and serving tampered binaries. Why can't the customer define static ip addresses?
* Wifi connectivity only: Which protocol? how to setup the password for the network?
* Services running with elevated rights
* Input / Output validation
