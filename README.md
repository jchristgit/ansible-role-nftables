# nftables Ansible Role

This (intentionally small) role allows you to manage the `nftables` firewall
on Debian Stable hosts.

## Usage

Include the `nftables` role in your dependencies. By default, this will only
allow SSH traffic (port `22`) to your host's IPv4 and IPv6 addresses.

To edit the configuration, change the `nftables_configuration` variable to
include the full, plaintext configuration file that you would like to deploy
on your server. You can also use `nftables_input_chain_rules` if you want to
append to the input chain rules manually.


## Configuration

### Optional variables

- `nftables_configuration` (string): Configuration file to template into
  `/etc/`. The firewall is reloaded on changes. For the default, see
  [`defaults/main.yml`](./defaults/main.yml). Note that SSH is enabled by
  default and if you choose to edit your configuration file yourself, take
  care not to lock yourself out.

- `nftables_input_chain_rules` (list[string]): List of rules to place in the
  input chain. Defaults to `[]`.

<!-- vim: set textwidth=80 sw=2 ts=2: -->
