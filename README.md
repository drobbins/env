# env

An experiment in creating a template portable development environment.

To bootstrap:

```
git submodule add https://github.com/drobbins/env.git env
git submodule init && git submodule update
cd env
vagrant up
```

Modify `replicator.yml` and `Vagrantfile` as necessary (e.g. open ports).
