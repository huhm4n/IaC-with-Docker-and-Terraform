[![Per Scholas](../per_scholas.png)](https://www.perscholas.org) 

# Install

## Install Terraform

### Download
 
- Download windows binary for terraform. [https://releases.hashicorp.com/terraform/1.3.1/terraform_1.3.1_windows_amd64.zip]
- Create terraform dir and create bin dir within your workspace
- Unzip and move binary to bin dir

```markdown
- __terraform__
  - __bin__
    - [terraform.exe](bin/terraform.exe)
  - __apache__
    - [main.tf](apache/main.tf)
```

### Setting Variable

- Open Environment Variables from Advanced System Settings
- Set the location where we’ve created terraform folder as TERRAFORM_HOME
- Edit Path with “$TERRAFORM_HOME/bin

## Author
Manish Ojha