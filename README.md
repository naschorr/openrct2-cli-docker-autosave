# openrct2-cli-docker-autosave
Based on the awesome [openrct2-cli](https://hub.docker.com/r/openrct2/openrct2-cli/dockerfile/) container from the OpenRCT2 team.

This container will automatically load your headless OpenRCT2 dockerized server's latest autosaved map. If one isn't available, it can load your base park file. Currently defaults to release [v0.2.3](https://openrct2.org/downloads/releases/v0.2.3), but that can be configured by setting the `OPENRCT2_REF` container variable.

### Running It
- Clone/Pull into `openrct2-cli-docker-autosave/`
- `docker build -t openrct2-cli-docker-autosave openrct2-cli-docker-autosave/`
- `docker run --rm -p 11753:11753 -v <Local path to OpenRCT2 config folder>:/home/openrct2/.config/OpenRCT2 -it openrct2-cli-docker-autosave`. Make sure you change the local path to your OpenRCT2 config folder. 

Also, you no longer need to specify `host <Path to park file>`, as that's taken care of in the Dockerfile's `ENTRYPOINT`.

### Unraid
Here's an example configuration within Unraid:

![Unraid example configuration image](https://raw.githubusercontent.com/naschorr/openrct2-cli-docker-autosave/master/resources/unraid_config_example.png)

### Note
This assumes that your container's folder structure is the same as the default that [openrct2-cli](https://hub.docker.com/r/openrct2/openrct2-cli/dockerfile/) expects, and it can't be changed without modifying the Dockerfile. Your default park save needs to be called `park.sv6`, otherwise the script won't detect it.