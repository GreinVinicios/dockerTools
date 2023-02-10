# dockerTools
This repo contains a docker file which creates an image with some tools pre-installed.
To change anything, simple add or remove things on [dockerfile](./dockerfile).

To run, execute following commands:
  
```bash
docker build -t greinvinicios/dockertools:latest .

docker push greinvinicios/dockertools:latest

docker run --name docker_dev --rm -it \
--mount type=bind,src=$(pwd),dst=/root \
--volume $HOME/.aws:/root/.aws \
--volume $HOME/.config/gcloud:/root/.config/gcloud \
greinvinicios/dockertools:latest /bin/bash
```
