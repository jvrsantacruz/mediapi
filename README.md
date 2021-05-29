# mediapi

Media center in raspberry based in docker compose.

Combines kodi, radarr, jackett, transmission and duckdns to search and download
media in your raspberry automatically.

## Config

Create a _.env_ file in the root directory with the following variables:


    # Replace to use in the raspberry
    BASE=debian:buster
    #BASE=balenalib/rpi-raspbian:buster

    # Replace with your path to the library
    MEDIA_DIR=./media

    # Common user and password
    USERNAME=YOUR_USER
    PASSWORD=YOUR_PASS

    DUCKDNS_DOMAINS=domain1,domain2
    DUCKDNS_TOKEN=

    NGINX_CONFIG=./nginx/config
    RADARR_CONFIG=./radarr/config
    JACKETT_CONFIG=./jackett/config
    TRANSMISSION_CONFIG=./transmission/config
    EMBY_CONFIG=./emby/config
