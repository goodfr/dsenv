# DS env

## Debug

### setup WSL

as [per the doc](https://learn.microsoft.com/fr-fr/windows/wsl/setup/environment)

```ps1
# in ps1
wsl -u root

# in opened wsl
user=devcontainers
echo user=$user
passwd $user
```

### Docker

as per [ref](https://docs.docker.com/engine/install/linux-postinstall/)

```sh
sudo groupadd docker

USER=devcontainers
sudo usermod -aG docker $USER
newgrp docker

# test
docker run hello-world
```

## Reproducibility

Use bash to avoid headache of writing utf-8 with powershell...

```sh
# when starting using conda-env use it twice...
conda env export --from-history > env.yml
conda env create --name test_recreate --file env.yml

# test without conda-env
conda export --from-history > env2.yml
mamba create --name test_recreate2 --file env2.yml
```
