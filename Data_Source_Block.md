data-source-01.tf

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

data-source-02.tf

data "local_file" "foo" {
  filename = "${path.module}/demo.txt"
}

output "data" {
    value = data.local_file.foo.content
}

data-source-03.tf

provider "aws" {
    region = "us-east-1"
}

data "aws_instances" "example" {}

