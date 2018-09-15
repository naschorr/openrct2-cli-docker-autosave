# openrct2-cli-docker-autosave
Automatically load your headless OpenRCT2 docker container's latest autosaved map. If one isn't available, it can load your base park file.

### Running It
- Clone/Pull into `openrct2-cli-docker-autosave/`
- `docker build -t openrct2-cli-docker-autosave openrct2-cli-docker-autosave/`
- `docker run --rm -p 11753:11753 -v <Local path to OpenRCT2 config folder>:/home/openrct2/.config/OpenRCT2 -it openrct2-cli-docker-autosave`. Make sure you change the local path to your OpenRCT2 config folder. Also, you no longer need to specify `host <Path to park file>`, as that's taken care of in the Dockerfile's `ENTRYPOINT`.

### Note
This assumes that your container's folder structure is the same as the default that OpenRCT2 expects, and it can't be changed without modifying the Dockerfile. Your default park save needs to be called `park.sv6`, otherwise the script won't detect it.