---
---

# Requirements Checklist

You MUST NOT continue to installation until you've worked through the checklists below. Environmental preperation is critical to a successful outcome.

## Required Checklist

1. A **dedicated** CentOS 7 server, likely a Virtual Machine, with the following minimum specifications:

    1. 2 CPU
    1. 2GB RAM
    1. 10GB+ partition for OS

    This server MUST NOT be used for any other purpose in the future.
2. You MUST have SSH access to the server
3. You MUST be able to execute commands as `root` on the system without limitation
4. The server MUST be routable from the public internet with a static IP. Often this means configuring the IP on a local network interface directly but advanced environments may handle this differently.

5. The static IP MUST be provided with a publicly resolvable DNS entry. Typically of the form `idp.example.edu`
6. The server MUST be able to communicate with the wider internet without blockage due to firewall rules. All publicly routable servers MUST be accessible for:

    | Port | Purpose |
    |------|---------|
    | 80   | Outbound HTTP connections |
    | 443  | Outbound HTTPS connections |

    Each of the following commands MUST succeed when run *on your server*:

      1. `curl http://example.edu`
      2. `curl https://example.edu`

7. The server MUST be accessible from the wider internet without blockage due to firewall rules for:

    | Port | Purpose |
    |------|---------|
    | 80   | Inbound HTTP connections used within SAML flows  |
    | 443  | Inbound HTTPS connections used within SAML flows  |
    | 8443 | Backchannel, client verified TLS connections, used within SAML flows |

9. Environmental data pertaining to your IdP

    1. A determination of the AAF federation you wish to register your IdP within, being test or production. AAF Support can assist you in determining this
    1. Organisation Name
    1. Organization base domain e.g. `example.edu`

## Optional Checklist

1. An account which can bind to and run queries against your corporate directory service. You'll require the following pieces of information from your directory administrator:

    1. IP Address / DNS entry for your LDAP server and connection port
    2. Base DN for user objects within your directory
    3. The Bind DN of the account you wish to connect to the directory with
    4. The password for the above account
    5. An LDAP filter attribute, often `uid`

    Without LDAP details available you'll need to undertake additional customisation post installation to configure an identity source.

## Next Step

Once you've finalised these checklists please continue to the [installation](installation.html) stage.