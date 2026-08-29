# Threat Model

## Internal employees

* Objective: keep them from leaking the data

### Ops

* Ops employee dumps the DB
* Ops employee logs into the DB
  * extract data
  * modify data
  * delete data
* Ops employee deletes DB
  * by accident
  * intentionally
* ops employee copies a DB Backup
* applies wrong configuration
* permissions
  * elevate own permissions
  * add permissions to other users
  * create users
  * leak credentials
* man-in-the-middle the infrastructure (requests to DB)
* root access to AWS leak
  * in code repository
  * in paper

### Dev

* Production data in test env
  * Abuse of PII
* Bad configuaration / misconfiguration
* Backdoor the code

### Admin

* Give access to external people (non employee)
* IAM Manipulation
* Reset customer credentials + identity overtake
* Extract audit login events
  * user log in / log out

### Support

* Reset customer credentials + identity overtake
* Obtain the PII 
* Obtain pci-dss (credit card data) data
* Change data without approval
* Check customer data for personal gain

## Pet Shop Owner

* Subdomain hijacking
  * Setup the same shop after it closes, to steal from customers
* Brute force another shop's owner account
* Check other shops bookings in the same area
* Create customer accounts with another shop and make appointments
* Block subdomains by registering many

## Pet Shop Customer

* Use stolen credit cards
* Abuse coupon functionality
* Guess coupon codes (maybe left overs from dev/testing)
* Log on as somebody else
* Access another user's account (e.g. uri, jwt manipulation)
* Tamper with local data in the browser (e.g. session data, cookies)
* Escalate rights/privileges (e.g. session data, guessing admin credentials, look at source code in SPA)

## Technical Threats

