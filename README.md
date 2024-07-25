# Docker with PHP 8.3.4 and MySQL 8
Web development environment setup for UNIX.

## To use the PHP Executable from the Docker Container

1. Find the PHP path inside the docker container

```bash
docker exec -it docker.php bash
which php
```

2. Create a wrapper script `docker-php` to run PHP commands via docker

```bash
# for example: the current PATH is /usr/local/bin
sudo nano /usr/local/bin/docker-php
```

3. Add the following code

```bash
#!/bin/bash
docker compose exec docker.php php "$@"
```

4. Make the script executable

```bash
sudo chmod +x /usr/local/bin/docker-php
```

5. Use the new script to run PHP commands in your machine

```bash
docker-php -v
docker-php -r 'echo "Hello from Docker PHP!\n";'
```
