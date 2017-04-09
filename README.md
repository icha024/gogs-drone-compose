## Setup Gogs with Drone CI

Hook for git commit injects 'localhost' because it detects the entrypoint of request to DroneCI. Manually update it or fix DroneCI code: https://github.com/drone/drone/blob/240f2a8ec520003a6c7a66a7236a742d4d665a06/shared/httputil/httputil.go#L50

## Ubuntu
```mkdir /var/lib/gogs
mkdir /var/lib/drone
docker-compose up```

Note: you may need to update docker: `sudo pip install docker`
