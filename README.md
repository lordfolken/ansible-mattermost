mattermost
==========

Mattermost platform setup


Role Variables
--------------

```yaml
mattermost_version: MATTERMOST_VERSION
mattermost_team_name: YOUR_TEAM_NAME (ONLY ALLOW [a-zA-Z0-9_])
mattermost_domain_name: YOUR_DOMAIN_NAME_OF_MATTERMOST_WEB_SITE
mattermost_user: USER_ACCOUNT_THAT_RUNNING_MATTERMOST_SERVICE (default: mattermost)
mattermost_group: GROUP_ACCOUNT_THAT_RUNNING_MATTERMOST_SERVICE (default: mattermost)
mattermost_db_user: MATTERMOST_DB_USER (default: {{ mattermost_team_name }})
mattermost_db_password: MATTERMOST_DB_PASSWORD
mattermost_db_name: MATTERMOST_DB_NAME (default: {{ mattermost_team_name }})
mattermost_root_dir: MATTERMOST_ROOT_DIR (default: /opt/{{ mattermost_team_name }}_mattermost)
mattermost_port: MATTERMOST_PORT (default: 8065)
```

Dependencies
------------

- pylabs.nginx
- pylabs.percona
- pylabs.letsencrypt

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - role: pylabs.mattermost
  vars:
    mattermost_version: "4.6.1"
    mattermost_team_name: myteam
    mattermost_domain_name: "chat.pylabs.org"
    mattermost_db_password: mattermost
    mattermost_port: 8065
```

License
-------

MIT

Author Information
------------------

William Wu
