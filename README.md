This is me trying to run the dockerfile of bountysource.com

# Using the dockerfile

```
docker run -p 80:3000 -it bountsource/core:latest 
docker build -t bountsource/core:latest .
```

This is still missing the env vars. For the env vars lists, check files:
* env-config
* env-nonconfig-nonbsenv
* env-nonconfig-bsenv
