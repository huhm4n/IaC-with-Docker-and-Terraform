[![Per Scholas](../per_scholas.png)](https://www.perscholas.org) 

# Apache in Container

## main.tf 

```
terraform {
  required_providers {
    docker = {
      source  = "kreuzwerker/docker"
      version = "2.22.0"
    }
  }
}

provider "docker" {
  host     = "ssh://root@107.21.194.107:22"
  ssh_opts = ["-o", "StrictHostKeyChecking=no", "-o", "UserKnownHostsFile=/dev/null"]
}

# Pulls the image
resource "docker_image" "httpd" {
  name = "httpd:latest"
}

# Create a container
resource "docker_container" "apache" {
  image = docker_image.httpd.image_id
  name  = "apache"

ports {

external = 8080
internal = 80

}
}

```

## terraform init

**Initializes working direcory containing terraform configuration files**

```
terraform init
```

## terraform format 

**Rewrites terraform config fiels to a canonical format and style**

```
terraform fmt main.tf
```

## terraform plan 

**Creates an execution plan and let us preview the changes**

```
terraform plan main.tf
```

## terraform apply

**Terraform apply commands executes the action propsed in terraform plan to create, update or detroy infrastructure**
```
terraform apply main.tf
```

## terraform state

**local file to save terraform state by default**

```
cat terraform.tfstate
```

## Author
Manish Ojha