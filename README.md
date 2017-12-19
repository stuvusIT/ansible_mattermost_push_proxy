# mattermost-push-proxy

This role sets up a Mattermost push proxy.
You need the proper API keys for this to work.

## Requirements

Ubuntu

## Role Variables

| Name                                               | Default/Required        | Description                                                                                                                                               |
|----------------------------------------------------|:-----------------------:|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| `mattermost_push_proxy_version_short`              | `4.4`                   | First two parts of the version of the push proxy                                                                                                          |
| `mattermost_push_proxy_version`                    | `4.4.0`                 | Version of the push proxy to install                                                                                                                      |
| `mattermost_push_proxy_user`                       | `mattermost-push-proxy` | User to run the push proxy under                                                                                                                          |
| `mattermost_push_proxy_address`                    | `127.0.0.1:8066`        | Port and optional host to listen on                                                                                                                       |
| `mattermost_push_proxy_throttle_per_sec`           | `300`                   | Throttle the requests per seconds                                                                                                                         |
| `mattermost_push_proxy_throttle_memory_store_size` | `500000`                | Size of the throtteled store                                                                                                                              |
| `mattermost_push_proxy_throttle_vary_by_header`    | `X-Forwarded-For`       | Header with the client IP                                                                                                                                 |
| `mattermost_push_proxy_apple`                      | `[]`                    | List of Android configuration specifications. See the [official documentation](https://github.com/mattermost/mattermost-push-proxy/blob/master/README.md) |
| `mattermost_push_proxy_android`                    | `[]`                    | List of Apple configuration specifications. See the [official documentation](https://github.com/mattermost/mattermost-push-proxy/blob/master/README.md)   |


## Example Playbook

```yml
- hosts: mattermost
  roles:
  - mattermost-push-proxy
     mattermost_push_proxy_throttle_per_sec: 500
     mattermost_push_proxy_address: ":8065"
```

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/).

## Author Information

- [Janne Heß](https://github.com/dasJ)
