# Ansible script for setting up my laptop WIP
# MANJARO - arch based
## todo:
  - solve netcore install
  - nvm install and set node
  - inotify
  - docker conatiners
  - setup backup stuff
  - dotfiles

run with:
```bash
ansible-playbook -i "localhost," -c local dev-machine.yml  --ask-sudo-pass
```

May ask for password sometimes

Change vars in dev-machine.yml

After install:
remeber to increase inotify limit
```bash
echo fs.inotify.max_user_watches=524288 | sudo tee /etc/sysctl.d/40-max-user-watches.conf && sudo sysctl --system
```

----------

docker:

```bash
docker volume create portainer_data
docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer
```

```bash
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=yourStrong(!)Password' -p 1433:1433 -d microsoft/mssql-server-linux:latest
```

```bash
docker run --name mysql -e MYSQL_ROOT_PASSWORD=asdf1234 -d mysql:latest
```
