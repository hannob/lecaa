# lecaa
Check for Let's Encrypt CAA issue

usage
-----

Prepare list of serials:

 ./prepare-lecaa

(This will download a list of affected certificates, extract the
serial numbers and sort them.)

Run:

 ./lecaa [host]

It will output affected hosts and be silent for unaffected hosts.

This can be used in combination with GNU parallel to check a large
number of hosts:

 parallel -a [list_of_hosts] -j 30 --timeout 10 ./lecaa

background
----------

Let's Encrypt announced a bug in their system's CAA checks, which forced
them to revoke 3 million certificates on very short notice.

This script allows you to efficiently check affected hosts.

* https://community.letsencrypt.org/t/revoking-certain-certificates-on-march-4/114864
* https://www.golem.de/news/tls-let-s-encrypt-muss-drei-millionen-zertifikate-zurueckziehen-2003-146999.html

who
---

Written by Hanno Böck, https://hboeck.de/
