# Nextcloud Compose

One more docker compose recipe to deploy Nextcloud.

## How does it work

First, you need to set secrets for docker compose. The folder secrets holds a list of files where you can set usernames and passwords for your Nextcloud installation.

Once that is done, you can deploy with `docker-composer up`

## Notes

This Nextcloud installation is supposed to be run behind a reverse proxy.

At the time of writing, Nextcloud does not support Postgres 16 ([ref](https://docs.nextcloud.com/server/25/admin_manual/installation/system_requirements.html)). So for the moment I pinned version 15, but this might change in the future. 


