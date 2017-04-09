## Setup Gogs with Drone CI

### Setup on Ubuntu

Note: you may need to update docker: `sudo pip install docker`
```
mkdir /var/lib/gogs
mkdir /var/lib/drone
docker-compose up
```

Configure Gogs:
http://localhost:8081
- Use SQLite3
- Set SSH port to 10022
- Set 'Application URL' to use your `hostname:8081`
- Create admin user 'ian'
- (Recommended) Enable 'Use builtin SSH server'
- (Recommended) Disable 'Self registration'
- (Recommended) Enable 'Require sign in to view page'

Configure Drone:
http://localhost:8080

Restart with `docker-compose up`

### HA Proxy
HA Proxy rewrite the git hook name to the internal docker-compose name, otherwise it would be localhost: https://github.com/drone/drone/blob/240f2a8ec520003a6c7a66a7236a742d4d665a06/shared/httputil/httputil.go#L50
