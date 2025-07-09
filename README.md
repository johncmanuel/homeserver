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
