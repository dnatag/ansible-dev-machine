# Ansible script for setting up my laptop WIP
# MANJARO - arch based
## todo
  - solve netcore install
  - nvm install and set node

run with:
```bash
ansible-playbook -i "localhost," -c local dev-machine.yml  --ask-sudo-pass
```

May ask for password sometimes

Change vars in dev-machine.yml

After install:
remeber to increase inofy limit
```bash
echo fs.inotify.max_user_watches=524288 | sudo tee /etc/sysctl.d/40-max-user-watches.conf && sudo sysctl --system
```
