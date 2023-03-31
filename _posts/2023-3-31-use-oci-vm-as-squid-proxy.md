To use an Oracle Cloud Infrastructure VM as Squid proxy

1. Install squid and apache2-utils

    ```
    sudo apt update
    sudo apt install squid
    sudo apt install apache2-utils
    ```

1. Generate password file

    ```
    sudo htpasswd -c /etc/squid/passwords your_squid_username
    ```

1. Configure squid

    ```
    sudo nano /etc/squid/squid.conf
    ```

    ```
    ...
    include /etc/squid/conf.d/*
    auth_param basic program /usr/lib/squid/basic_ncsa_auth /etc/squid/passwords
    auth_param basic realm proxy
    acl authenticated proxy_auth REQUIRED
    # Example rule allowing access from your local networks.
    # Adapt localnet in the ACL section to list your (internal) IP networks
    # from where browsing should be allowed
    http_access deny !authenticated
    http_access allow localnet
    http_access allow localhost
    http_access allow all

    # And finally deny all other access to this proxy
    http_access deny all
    ...

1. Restart squid

    ```
    sudo systemctl restart squid.service
    ```

1. Add TCP/3128 to iptables

    ```
    sudo iptables -I INPUT 6 -m state --state NEW -p tcp --dport 3128 -j ACCEPT
    sudo netfilter-persistent save
    ```
