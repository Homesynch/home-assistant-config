# home-assistant-config

# Development environment
In order to setup the development environment so you can test your ansible scripts execute the following:

1. run `install_roles` script;
2. run `docker/setup_env` script;
3. run `ansible-playbook -i inventories/dev playbooks/installation.yml`

If everything goes well, you should see the following output (or very similar):

Not there are no failed tasks (`failed=0`)
```
PLAY RECAP *****************************************************************************************************************************************************
127.0.0.1                  : ok=11   changed=2    unreachable=0    failed=0    skipped=9    rescued=0    ignored=0   
```

At this point in time you should be able to access the HA under `http://localhost:8123`