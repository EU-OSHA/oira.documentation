# oira.documentation
*EU-OSHA - OIRA - Technical documentation*

This package uses sphinx to create the HTML version of the technical documentation for OIRA.

# Installation

Clone the package using git:

```bash
git clone https://github.com/EU-OSHA/oira.documentation.git
```

# Creating the documentation

Run make:

```bash
make html
```

The documentation is now available under `build/html`. 

When running for the first time the make command will initialize a virtualenv and run buildout.
This will install sphinx, clone the necessary packages and set everything else up.

# Hosting the documentation

Create an entry for your webs-server and let the root point to the directory mentioned above. Below is an example for nginx. Adapt the the `server_name` and `root` according to your needs.

```nginx
server {
        listen 80;
        server_name oiradoc.syslab.com;
        root /home/oira/oira.documentation/build/html;
        charset utf-8;
        autoindex on;
        override_charset on;
        gzip on;
        gzip_min_length 1100;
        gzip_buffers 4 8k;
        gzip_types text/plain;
        gzip_static on;
        client_max_body_size 128M;

    location  /robots.txt {
        alias /var/www/Euphorie/robots.txt;
    }

    access_log  /var/log/nginx/oiradoc-access.log;
}
```

