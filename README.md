# oira.documentation
*EU-OSHA - OIRA - Technical documentation*

This package uses sphinx to create the HTML version of the technical documentation for OIRA.

# Installation

Clone the package using git:

```bash
git clone https://github.com/EU-OSHA/oira.documentation.git
```

Create a virtual python environment, then activate it:

```bash
virtualenv .
source bin/activate
```

Install the buildout requirements, then run buildout:

```bash
pip install -r requirements.txt
bin/buildout
```

This will clone the necessary packages from git/mercurial.

# Creating the documentation

Switch to the build directory and run make:

```bash
cd build
make html
```

The documentation is now available under `build/html`. 

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

