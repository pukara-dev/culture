# culture

This repository holds Pukara's [culture website](https://culture.pukara.dev)

## Contribute

To contribute clone this repository and spin up a the local image with `make`:

```sh
$ make dev
docker run --rm -it -p 8000:8000 -v /Users/mogaal/workspace/culture:/docs squidfunk/mkdocs-material
WARNING  -  Config value 'dev_addr': The use of the IP address '0.0.0.0' suggests a production environment or the use of a proxy to connect to the MkDocs server. However, the
            MkDocs' server is intended for local development purposes only. Please use a third party production-ready server instead.
INFO     -  Building documentation...
INFO     -  Cleaning site directory
INFO     -  Documentation built in 1.30 seconds
INFO     -  [09:55:48] Watching paths for changes: 'docs', 'mkdocs.yml'
INFO     -  [09:55:48] Serving on http://0.0.0.0:8000/
INFO     -  [09:55:52] Browser connected: http://localhost:8000/
```

Make the required changes, mkdocs is going to watch for changes on `docs/` folder so no reload needed
