# terraform-aws-vpc-peering

Terraform module for VPC peering

```
provider "aws" {

}

module "peering_connection" {
  source = "github.com/sivakumarvunnam/terraform-aws-vpc-peering"

  providers = {
    aws.this = aws
    aws.peer = aws
  }

  this_vpc_id                    = "source vpc id"
  this_vpc_route_table_ids       = "source vpc id routing tables ids"
  allow_this_resolve_dns_in_peer = true
  allow_peer_resolve_dns_in_this = false

  peer_vpc_id                    = "peer vpc id"
  auto_accept_peering_connection = true
}
```
