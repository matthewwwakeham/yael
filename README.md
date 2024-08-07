# yael

## Setup
These commands are used when first setting up the server.

```
docker-compose up -d helloworld
docker-compose up -d
docker-compose up -d nginx
docker-compose up -d certbot
docker-compose up
```

## Certbot manual setup
You must first create an A record pointing your domain to the IP address of the server.

Use the command below to generate SSL certificates with certbot manually.

```
sudo certbot certonly --webroot -w /var/www/html -d yourdomain.com -d www.yourdomain.com
```

Verify that certificates exist in /etc/letsencrypt. Directories for live, renewal, etc. should be located there. If the directories don't exist then the certificates were probably not created even if the nginx.conf certbot command was run and indicates otherwise.

## References
https://www.programonaut.com/setup-ssl-with-docker-nginx-and-lets-encrypt/
