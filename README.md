## Setup Gogs with Drone CI

### Setup on Ubuntu

```
docker-compose up
```

### Configure Gogs:
http://localhost:3000
- Use SQLite3
- Set SSH port to (blank) and disable it.
- Set 'Application URL' to your hostname and port 3000 (`my-host-name:3000`)
- Create admin user
- (Recommended) Disable 'Self registration'

**IMPORTANT:** The application URL hostname must not be 'localhost' because it need to be resolvable from the Drone agent. Use your machine's hostname instead. On Linux you may use the `hostname` command.

### Configure Drone:
http://localhost:8000

Use your Gogs admin username/password to login.

Once are repository is created in Gogs, it will show up here with the option to switch 'on'. Then a `.drone.yml` file is needed to actually do a build.

## Known issue:
- Drone doesn't seem be able to clone via HTTP when 'Require sign in to view page' options is enabled on Gogs.

## ToDo:
- [ ] Map Git SSH port and test it.
