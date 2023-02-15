# Quick and dirty list of vulnerabilities

## Inconsistencies

1. Customer swipes the card and the kiosk sends the information via the REST api to the admin service which calls the payment service ( See D1 for details )

The detail image has no such flow, but on to the order service flow (number 6) it states:

The Kiosk communicates order and payment information to the order services to
process the order.

2. Unencrypted comm to the order service from the printers, but port 80 is not open on the firewall. So, no printing?

3. Payment service and DB. High level description (D1): [...] payment service then writes the payment token to the database and releases the order for delivery to the food prep staff
There is no such dataflow in the detailed description. So that must be taken care of by the order service as well.
