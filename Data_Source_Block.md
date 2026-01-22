
**TEST**
## Code Used In Video:

### data-source-01.tf
```sh
terraform {
  required_providers {
    digitalocean = {
      source  = "digitalocean/digitalocean"
    }
  }
}

provider "digitalocean" {
  token = "your-token-here"
}

data "digitalocean_account" "example" {}
```
