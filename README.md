# Docker-Nginx-Certbot-Odoo-PG 

This simple example shows how to set up an Odoo instance running behind a dockerized Nginx reverse proxy and served via HTTPS using free Let's Encrypt certificates by Certbot. New sites can be added on the fly by just modifying docker-compose.yml and then running docker-compose up as the main Nginx config is automatically updated and certificates (if needed) are automatically acquired.

# Running

In the main directory run:

docker-compose up

This will perform the following steps:

    Download the required images from Docker Hub (Nginx, Certbot, PostgreSQL, pgAdmin and Odoo).
    Create containers from them and start up the containers.
    
If everything went well then you should now be able to access your website at the provided address.


# How does it work

The system consists of 4 main parts:

    Main Nginx reverse proxy container.
    Container that generates the main Nginx config based on container metadata.
    Container that automatically handles the acquisition and renewal of Let's Encrypt TLS certificates.
    The actual websites living in their own containers.
