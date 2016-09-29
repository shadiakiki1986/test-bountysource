This is me trying to run the dockerfile of bountysource.com

# Using the dockerfile

I thought of using the [bountysource/core:master](https://hub.docker.com/r/bountysource/core/tags/)
image on hub.docker.com, but it's 2 months old, so I decided to build my own.

```
git clone https://github.com/bountysource/core bountysource-core
cd bountysource-core
docker run -p 80:3000 -it bountysource/core:local
docker build -t bountysource/core:local .
```

The problem with this is that it is still missing the env vars.
For the env vars lists, check files:
* env-config
* env-nonconfig-nonbsenv
* env-nonconfig-bsenv

I need to work through them and set up what I need

Starting with the database env var,
I set up a `docker-compose.yml` file,
with a database initialization line from the `.travis.yml` file,
but `postgres` requires setting up a non-privileged user.
Besides, bountysource still complains about missing other env vars
