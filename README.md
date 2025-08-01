# personal server

only for use in a local network accessible via tailscale

## todo

reduce number of env variables

## setup

create a .env file at the root of the project with the following variables:
```
UID={user id}
GID={group id}

JELLYFIN_CONFIG={path to jellyfin config}
JELLYFIN_CACHE={path to jellyfin cache}
JELLYFIN_MOVIES={path to your movies}
JELLYFIN_TV={path to your tv shows}
```

## commands

to start:

`docker compose up --remove-orphans -d`

to end

`docker compose down`

## using HTTPS

Enable HTTPS for tailscale in the admin settings. If no domain, use the one provided by tailscale (e.g., `hostname.<random words>.ts.net`).

After that, run `sudo tailscale cert <domain give by tailscale>` to generate a TLS certificate for the server (your `hostname`).

Then run `sudo tailscale serve <port number of service you want HTTPS>` and access it at `https://hostname.<random words>.ts.net` (a reverse proxy *may* work if you want to serve multiple services with HTTPS at same domain, AFAIK)
