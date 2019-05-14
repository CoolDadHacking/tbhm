# Information Gathering
-----------------------
## Target Validation

This means find the application (or parts of an application) less tested. In wide scoped projects the flagship application will most likely be heavily assessed. 

- ^.acme.com scope is your friend
- Find domains via Google (and others!)
- Port scan for obscure web servers or services (on all domains)
- Find acquisitions and the bounty acquisition rules
  - Google has a 6 month rule
- Functionality changes or re-designs
- Mobile websites
- New mobile app versions
- Searching parent company by trademark or privacy policy

## Tool: Recon-ng script (enumall.sh)
https://github.com/jhaddix/domain

## ￼LMGTFY: Let Me GOOGLE That For You
site:paypal.com -www.paypal.com -www.sandbox

## List of Mergers and Acquisitions:
https://en.wikipedia.org/wiki/List_of_mergers_and_acquisitions_by_Facebook

## DNS Interrogation
```
https://dnsdumpster.com
dig +nocmd example.com A +noall +answer
dig +nocmd example.com NS +noall +answer
dig +nocmd example.com MX +noall +answer
dig +nocmd example.com TXT +noall +answer
dig +nocmd example.com SOA +noall +answer
...
dig +nocmd example.com ANY +noall +answer (This rarely works)
```

## Port Scanning
Port scanning is not just for Netpen! A full port scan of all your new found targets will usually yield #win:

- separate web apps
- extraneous services
- Facebook had Jenkins Script console with no auth
- IIS.net had RDP open vulnerable to MS12_020

``nmap -sS -A -PN -p- --script=http-title dontscanme.bro``

(syn scan, OS + service fingerprint, no ping, all ports, http titles)
