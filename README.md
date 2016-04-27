# Metasploit Framework dockerfile

# Purpose

This Dockerfile builds a Debian-based Docker container with Metasploit-Framework installed.

MSF is started automatically with:

- all dependencies installed,
- automatic updates at startup,
- a connection with the local Postgres database,
- an improved prompt with timestamping and sessions/jobs status.

# Build

To build the container, just use this command:

```
docker build -t debian-msf .
```

Docker will download the Debian image and then execute the installation steps.

# Run

Once the build process is over, get and enjoy a neat msf prompt with this command:

```
docker run -i -t -p 9990-9999:9990-9999 debian-msf
```

Here, we map the port range from 9990 to 9999 to our host, to catch reverse shells back.

Of course, it is up to you to adjust it to your taste or need.

# Shell access

If for some reason, you need to access to the shell, type this command from within the msf instance :

```
/bin/bash
```

You may also launch bash from Docker:

```
docker exec -i -t debian-msf /bin/bash
```
