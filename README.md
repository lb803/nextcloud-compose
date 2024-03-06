# Nextcloud Compose

One more docker compose recipe to deploy Nextcloud.

## Set Up

Firstly, you need to set secrets for docker compose. The folder secrets holds a list of files where you can set usernames and passwords for your Nextcloud installation.

Next, grab a copy of [the nginx config file](https://github.com/nextcloud/docker/blob/master/.examples/docker-compose/with-nginx-proxy/postgres/fpm/web/nginx.conf) from the reference nextcloud git repository (community docker) and save it in the same directory where you run this docker compose.

Once ready, you can deploy with `docker-composer up`

## Notes

### Reverse Proxy
This Nextcloud installation is supposed to be run behind a reverse proxy.

### PostreSQL
At the time of writing, Nextcloud does not support Postgres 16 ([ref](https://docs.nextcloud.com/server/25/admin_manual/installation/system_requirements.html)). So for the moment I pinned version 15, but this might change in the future.

### Backround Jobs
This docker compose does not come with a cron container. Should you wish to have the backround jobs run with cron, I suggest to simply run them on the host machine with: `*/5 * * * * docker exec -u www-data nextcloud-fpm php /var/www/html/cron.php`
