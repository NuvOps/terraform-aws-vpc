# AWS VPC Terraform module

Terraform module to create VPC resources on AWS.


![](https://www.nuvops.com/img/NuvOps-github.png)

Sponsored by [NuvOps LLC - DevOps as a Service](https://www.nuvops.com)


## Terraform versions

Terraform >= 0.12, < 0.13


## Usage

```hcl
module "vpc" {
  source = "nuvops/vpc/aws"

  name = "my-vpc"
  cidr = "10.0.0.0/16"

  azs             = ["us-east-1a", "us-east-1b", "us-east-1c"]
  private_subnets = ["10.0.1.0/24", "10.0.2.0/24", "10.0.3.0/24"]
  public_subnets  = ["10.0.101.0/24", "10.0.102.0/24", "10.0.103.0/24"]

  enable_nat_gateway = true

  tags = {
    Terraform = "true"
    Environment = "dev"
  }
}
```

## External NAT Gateway IPs

By default this module will provision new Elastic IPs for the VPC's NAT Gateways.
This means that when creating a new VPC, new IPs are allocated, and when that VPC is destroyed those IPs are released.



## Examples

TODO

<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|

TODO

## Outputs

| Name | Description |
|------|-------------|

TODO

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## Tests

TODO


## Contributing

Pull Requests are welcome. We follow the typical "fork-and-pull" Git workflow.

 1. **Fork** the repo on GitHub
 2. **Clone** the project to your own machine
 3. **Commit** changes to your own branch
 4. **Push** your work back up to your fork
 5. Submit a **Pull request** so that we can review your changes

## Consulting

If you need help adapting our templates for your project-specific needs we offer consulting services on demand. [Contact us](mailto:hi@nuvops.com)

## About

NuvOps specializes in Cloud Solutions and DevOps practices.
We accelerate startups from localhost to production-ready infrastructures.
Maintained by  [NuvOps LLC](https://www.nuvops.com)

## Authors

Module is maintained by [Libert Schmidt](https://github.com/rschmidtz)

## License

All templates are published under Apache License Version 2.0.
