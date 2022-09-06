# homelab-terraform-grafana-prometheus-consul-haproxy-traefik

# 🚀 monitoring grafana prometheus hashicorp observability homelab victoria-metrics 🚀

https://github.com/coding-to-music/homelab-terraform-grafana-prometheus-consul-haproxy-traefik

From / By https://github.com/nahsi-homelab/observability

Example of a Grafana dashboard, using data from Prometheus:

![The exporter container up and running](https://github.com/coding-to-music/terraform-cloudflare-prometheus-grafana/blob/main/images/image2-5.avif?raw=true)

![Grafana screenshot](https://github.com/coding-to-music/terraform-cloudflare-prometheus-grafana/blob/main/images/grafana_prometheus.png?raw=true)

## Digitalocean Droplet Prices

https://github.com/andrewsomething/do-api-slugs

https://slugs.do-api.dev

```
# https://slugs.do-api.dev/

# s-1vcpu-512mb-10gb  $4    10GB
# s-1vcpu-1gb         $6    25GB
# s-1vcpu-2gb         $12   50GB
# s-2vcpu-2gb         $18   60GB
# s-2vcpu-4gb         $24   80GB
# s-4vcpu-8gb         $48   160GB
```

## Quick Summary

terraform init

terraform plan

terraform apply -auto-approve

ssh -i /path/to/ssh-keyfile root@ip-address

https://dev.to/koddr/quick-how-to-clone-your-private-repository-from-github-to-server-droplet-vds-etc-39jm

ssh-keygen

put the id_rsa.pub contents into GitHub https://github.com/settings/keys

verify can clone from GitHub:

ssh -vT git@github.com

clone the docker project

run that

need to install terraform

https://www.terraform.io/downloads

wget -O- https://apt.releases.hashicorp.com/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list

sudo apt update && sudo apt install terraform

terraform -v

docker-compose -f docker-compose-step1.yml up

docker-compose -f docker-compose-step2.yml up

docker-compose -f docker-compose-step3.yml up

docker-compose -f docker-compose-step4.yml up

terraform destroy -auto-approve

## Status

Grafana

- set up Prometheus data source
- load dashboards

```

```

## Restart grafana-server:

```
sudo systemctl restart grafana-server
```

## Environment variables:

```java
// terraform.tvars.example

# Digitalocean Configuration
digitalocean_token = ""
digitalocean_droplet_image = "docker-20-04"
digitalocean_droplet_region = "lon1"
digitalocean_droplet_size = "s-1vcpu-1gb"
digitalocean_key_name = ""
digitalocean_priv_key_path = ""

# Cloudflare Configuration
cloudflare_domain = ""
cloudflare_account_id = ""
cloudflare_tunnel_secret = "Some-very-secret-passphrase-you-only-know"
cloudflare_cname_record = "grafana"
cloudflare_ssh_cname_record = "ssh-browser"

# Used by Terraform to manage your Cloudflare resources
cloudflare_api_token = ""
# Used by the Prometheus Exporter to pull your analytics from Cloudflare GraphQL
cloudflare_analytics_api_token = ""

# Authorized user for Cloudflare Access
user_email = ""
```

## GitHub

```java
git init
git add .
git remote remove origin
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:coding-to-music/homelab-terraform-grafana-prometheus-consul-haproxy-traefik.git
git push -u origin main
```

# Install Consul Server

https://blog.marcsg.com/consul-service-discovery-with-prometheus-and-grafana

```
# Update and install gnupg2 and curl for the following commands
apt-get update && apt-get install gnupg2 curl lsb-release

# Add consul's gpg key
curl -fsSL https://apt.releases.hashicorp.com/gpg | apt-key add -

# Add hashicorp's repository to our sources.list
echo "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main" > /etc/apt/sources.list.d/hashicorp.list

# Update and install consul
apt-get update && apt-get install consul

# Check Consul installation version
consul -v
```

## Status

```
terraform init

# output

Initializing the backend...

Error: Failed to get existing workspaces: Get "https://consul.service.consul/v1/kv/terraform/observability-env:?keys=&separator=%2F": dial tcp: lookup consul.service.consul on 127.0.0.53:53: no such host

```
