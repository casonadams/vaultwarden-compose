# vaultwarden

A simple example of using vaultwarden with
tailscale, caddy, docker-compose, and a raspberry pi

## setup

### setup caddy

[caddy install](https://caddyserver.com/docs/install)

### setup tailscale

[tailscale](https://tailscale.com/)

[tailnet-name](https://tailscale.com/kb/1217/tailnet-name/)

- Add a machine
- Setup DNS
- Enable MagicDNS
- Enable HTTPS Certificates

### docker

```sh
curl -sSL https://get.docker.com | sh
```

```sh
apt install docker-compose
```

### systemd units

- Modify the host name in `etc/caddy/Caddyfile` to reflect the `machine-name.tail.net`

```sh
cp etc/systemd/system/caddy.service /etc/systemd/system/caddy.service
cp etc/systemd/system/vaultwarden.service /etc/systemd/system/vaultwarden.service
```

- enable the service

```sh
systemctl enable caddy
systemctl enable vaultwarden
```

## run

- run the service

```sh
systemctl restart caddy
systemctl restart vaultwarden
```

- Use browser to visit https://mahine-name.tail.net
