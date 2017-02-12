# Ansible Role - SABnzbd

A role for managing a
[SABnzbd](https://github.com/CouchPotato/CouchPotatoServer) installation.

## Requirements

None.

## Role Variables

- `sabnzbd_systemd_supplementary_groups` - a list of groups keyed to the
  CouchPotato systemd unit's `SupplementaryGroups`.  Default is
  `['downloads']`.
- `sabnzbd_settings` - a hash of settings to merge into SABnzbd's
  configuration file.  By default the hash is empty.
- `sabnzbd_data_dir` - directory where SABnzbd should store its
  database, cache, and other data sources.  Defaults to
  `/var/data/sabnzbd`.
- `sabnzbd_config_file` - SABnzbd's configuration file.  Defaults to
  `{{ sabnzbd_data_dir }}/config.ini`.

## Example Playbook

```yaml
- hosts: sabnzbd
  roles:
    - role: BaxterStockman.sabnzbd
      sabnzbd_data_dir: '/opt/sabnzbd'
      sabnzbd_config_file: '/etc/sabnzbd.ini'
      sabnzbd_settings:
        core:
          port: 8111
        manage:
          library: /my/media/library
```

## License

MIT

## Author Information

Matt Schreiber <mschreiber@gmail.com>
