# terraform_ex soll3

## 실행
```

ubuntu@u1:/mnt/hgfs/Desktop/terraform_ex/sol3$ terraform init

Initializing the backend...

Initializing provider plugins...

The following providers do not have any version constraints in configuration,
so the latest version was installed.

To prevent automatic upgrades to new major versions that may contain breaking
changes, it is recommended to add version = "..." constraints to the
corresponding provider blocks in configuration, with the constraint strings
suggested below.

* provider.aws: version = "~> 2.60"

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan" to see
any changes that are required for your infrastructure. All Terraform commands
should now work.

If you ever set or change modules or backend configuration for Terraform,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.
ubuntu@u1:/mnt/hgfs/Desktop/terraform_ex/sol3$ terraform apply -auto-approve
aws_vpc.main: Refreshing state... [id=vpc-0ddc396c0ff4b02ab]
aws_subnet.main-private-3: Refreshing state... [id=subnet-058492f5659aae5bd]
aws_subnet.main-public-2: Refreshing state... [id=subnet-07a5bb8a119ed0295]
aws_internet_gateway.main-gw: Refreshing state... [id=igw-0c83f7bdb62175671]
aws_subnet.main-private-1: Refreshing state... [id=subnet-0e4e68a8fb5b7f932]
aws_subnet.main-public-1: Refreshing state... [id=subnet-03b119e5b8d9a8c2d]
aws_subnet.main-public-3: Refreshing state... [id=subnet-0d839e551d55605a2]
aws_subnet.main-private-2: Refreshing state... [id=subnet-03340a66d6fda6c04]
aws_security_group.allow-ssh: Refreshing state... [id=sg-06e8cc601eab204e5]
aws_route_table.main-public: Refreshing state... [id=rtb-056417eff78b9e96f]
aws_route_table_association.main-public-1-a: Refreshing state... [id=rtbassoc-0be59876e8a2b5331]
aws_route_table_association.main-public-3-a: Refreshing state... [id=rtbassoc-066fb03bf0211ada5]
aws_route_table_association.main-public-2-a: Refreshing state... [id=rtbassoc-071bf69778b837573]
aws_key_pair.mykey: Creating...
aws_key_pair.mykey: Creation complete after 3s [id=mykey]
aws_instance.example2: Creating...
aws_instance.example1: Creating...
aws_instance.example3: Creating...
aws_instance.example1: Still creating... [10s elapsed]
aws_instance.example2: Still creating... [10s elapsed]
aws_instance.example3: Still creating... [10s elapsed]
aws_instance.example2: Still creating... [20s elapsed]
aws_instance.example1: Still creating... [20s elapsed]
aws_instance.example3: Still creating... [20s elapsed]
aws_instance.example2: Still creating... [30s elapsed]
aws_instance.example1: Still creating... [30s elapsed]
aws_instance.example3: Still creating... [30s elapsed]
aws_instance.example2: Still creating... [40s elapsed]
aws_instance.example1: Still creating... [40s elapsed]
aws_instance.example3: Still creating... [40s elapsed]
aws_instance.example3: Creation complete after 42s [id=i-0c069f40f2086e5f2]
aws_instance.example2: Creation complete after 42s [id=i-009946c58b19b18f6]
aws_instance.example1: Creation complete after 42s [id=i-01531d36f75e02c62]

Apply complete! Resources: 4 added, 0 changed, 0 destroyed.

```

## 접속
```
ubuntu@u1:/mnt/hgfs/Desktop/terraform_ex/sol3$ ssh -i ~/mykey ubuntu@34.240.48.62
Warning: Permanently added '34.240.48.62' (ECDSA) to the list of known hosts.
Welcome to Ubuntu 20.04 LTS (GNU/Linux 5.4.0-1009-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Mon May 11 03:14:51 UTC 2020

  System load:  0.0               Processes:             99
  Usage of /:   16.2% of 7.69GB   Users logged in:       0
  Memory usage: 19%               IPv4 address for eth0: 10.0.3.129
  Swap usage:   0%

0 updates can be installed immediately.
0 of these updates are security updates.


The list of available updates is more than a week old.
To check for new updates run: sudo apt update


The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

To run a command as administrator (user "root"), use "sudo <command>".
See "man sudo_root" for details.

ubuntu@ip-10-0-3-129:~$ exit
logout
Connection to 34.240.48.62 closed.



```



## tfstate
```
{
  "version": 4,
  "terraform_version": "0.12.24",
  "serial": 47,
  "lineage": "49e75542-8678-6846-6c7e-74587da763b7",
  "outputs": {},
  "resources": [
    {
      "mode": "managed",
      "type": "aws_instance",
      "name": "example1",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 1,
          "attributes": {
            "ami": "ami-0dad359ff462124ca",
            "arn": "arn:aws:ec2:eu-west-1:431317591088:instance/i-01531d36f75e02c62",
            "associate_public_ip_address": true,
            "availability_zone": "eu-west-1a",
            "cpu_core_count": 1,
            "cpu_threads_per_core": 1,
            "credit_specification": [
              {
                "cpu_credits": "standard"
              }
            ],
            "disable_api_termination": false,
            "ebs_block_device": [],
            "ebs_optimized": false,
            "ephemeral_block_device": [],
            "get_password_data": false,
            "hibernation": false,
            "host_id": null,
            "iam_instance_profile": "",
            "id": "i-01531d36f75e02c62",
            "instance_initiated_shutdown_behavior": null,
            "instance_state": "running",
            "instance_type": "t2.micro",
            "ipv6_address_count": 0,
            "ipv6_addresses": [],
            "key_name": "mykey",
            "metadata_options": [
              {
                "http_endpoint": "enabled",
                "http_put_response_hop_limit": 1,
                "http_tokens": "optional"
              }
            ],
            "monitoring": false,
            "network_interface": [],
            "network_interface_id": null,
            "outpost_arn": "",
            "password_data": "",
            "placement_group": "",
            "primary_network_interface_id": "eni-0c39b558ed405e6ef",
            "private_dns": "ip-10-0-1-227.eu-west-1.compute.internal",
            "private_ip": "10.0.1.227",
            "public_dns": "ec2-54-154-134-112.eu-west-1.compute.amazonaws.com",
            "public_ip": "54.154.134.112",
            "root_block_device": [
              {
                "delete_on_termination": true,
                "device_name": "/dev/sda1",
                "encrypted": false,
                "iops": 100,
                "kms_key_id": "",
                "volume_id": "vol-0e691cfe47a1e8483",
                "volume_size": 8,
                "volume_type": "gp2"
              }
            ],
            "security_groups": [],
            "source_dest_check": true,
            "subnet_id": "subnet-03b119e5b8d9a8c2d",
            "tags": null,
            "tenancy": "default",
            "timeouts": null,
            "user_data": null,
            "user_data_base64": null,
            "volume_tags": {},
            "vpc_security_group_ids": [
              "sg-06e8cc601eab204e5"
            ]
          },
          "private": "eyJlMmJmYjczMC1lY2FhLTExZTYtOGY4OC0zNDM2M2JjN2M0YzAiOnsiY3JlYXRlIjo2MDAwMDAwMDAwMDAsImRlbGV0ZSI6MTIwMDAwMDAwMDAwMCwidXBkYXRlIjo2MDAwMDAwMDAwMDB9LCJzY2hlbWFfdmVyc2lvbiI6IjEifQ==",
          "dependencies": [
            "aws_key_pair.mykey",
            "aws_security_group.allow-ssh",
            "aws_subnet.main-public-1"
          ]
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_instance",
      "name": "example2",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 1,
          "attributes": {
            "ami": "ami-0dad359ff462124ca",
            "arn": "arn:aws:ec2:eu-west-1:431317591088:instance/i-009946c58b19b18f6",
            "associate_public_ip_address": true,
            "availability_zone": "eu-west-1b",
            "cpu_core_count": 1,
            "cpu_threads_per_core": 1,
            "credit_specification": [
              {
                "cpu_credits": "standard"
              }
            ],
            "disable_api_termination": false,
            "ebs_block_device": [],
            "ebs_optimized": false,
            "ephemeral_block_device": [],
            "get_password_data": false,
            "hibernation": false,
            "host_id": null,
            "iam_instance_profile": "",
            "id": "i-009946c58b19b18f6",
            "instance_initiated_shutdown_behavior": null,
            "instance_state": "running",
            "instance_type": "t2.micro",
            "ipv6_address_count": 0,
            "ipv6_addresses": [],
            "key_name": "mykey",
            "metadata_options": [
              {
                "http_endpoint": "enabled",
                "http_put_response_hop_limit": 1,
                "http_tokens": "optional"
              }
            ],
            "monitoring": false,
            "network_interface": [],
            "network_interface_id": null,
            "outpost_arn": "",
            "password_data": "",
            "placement_group": "",
            "primary_network_interface_id": "eni-0b7a7595138f6afde",
            "private_dns": "ip-10-0-2-92.eu-west-1.compute.internal",
            "private_ip": "10.0.2.92",
            "public_dns": "ec2-18-203-100-39.eu-west-1.compute.amazonaws.com",
            "public_ip": "18.203.100.39",
            "root_block_device": [
              {
                "delete_on_termination": true,
                "device_name": "/dev/sda1",
                "encrypted": false,
                "iops": 100,
                "kms_key_id": "",
                "volume_id": "vol-09fa0f98670a00e04",
                "volume_size": 8,
                "volume_type": "gp2"
              }
            ],
            "security_groups": [],
            "source_dest_check": true,
            "subnet_id": "subnet-07a5bb8a119ed0295",
            "tags": null,
            "tenancy": "default",
            "timeouts": null,
            "user_data": null,
            "user_data_base64": null,
            "volume_tags": {},
            "vpc_security_group_ids": [
              "sg-06e8cc601eab204e5"
            ]
          },
          "private": "eyJlMmJmYjczMC1lY2FhLTExZTYtOGY4OC0zNDM2M2JjN2M0YzAiOnsiY3JlYXRlIjo2MDAwMDAwMDAwMDAsImRlbGV0ZSI6MTIwMDAwMDAwMDAwMCwidXBkYXRlIjo2MDAwMDAwMDAwMDB9LCJzY2hlbWFfdmVyc2lvbiI6IjEifQ==",
          "dependencies": [
            "aws_key_pair.mykey",
            "aws_security_group.allow-ssh",
            "aws_subnet.main-public-2"
          ]
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_instance",
      "name": "example3",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 1,
          "attributes": {
            "ami": "ami-0dad359ff462124ca",
            "arn": "arn:aws:ec2:eu-west-1:431317591088:instance/i-0c069f40f2086e5f2",
            "associate_public_ip_address": true,
            "availability_zone": "eu-west-1c",
            "cpu_core_count": 1,
            "cpu_threads_per_core": 1,
            "credit_specification": [
              {
                "cpu_credits": "standard"
              }
            ],
            "disable_api_termination": false,
            "ebs_block_device": [],
            "ebs_optimized": false,
            "ephemeral_block_device": [],
            "get_password_data": false,
            "hibernation": false,
            "host_id": null,
            "iam_instance_profile": "",
            "id": "i-0c069f40f2086e5f2",
            "instance_initiated_shutdown_behavior": null,
            "instance_state": "running",
            "instance_type": "t2.micro",
            "ipv6_address_count": 0,
            "ipv6_addresses": [],
            "key_name": "mykey",
            "metadata_options": [
              {
                "http_endpoint": "enabled",
                "http_put_response_hop_limit": 1,
                "http_tokens": "optional"
              }
            ],
            "monitoring": false,
            "network_interface": [],
            "network_interface_id": null,
            "outpost_arn": "",
            "password_data": "",
            "placement_group": "",
            "primary_network_interface_id": "eni-06a5123d91608c612",
            "private_dns": "ip-10-0-3-129.eu-west-1.compute.internal",
            "private_ip": "10.0.3.129",
            "public_dns": "ec2-34-240-48-62.eu-west-1.compute.amazonaws.com",
            "public_ip": "34.240.48.62",
            "root_block_device": [
              {
                "delete_on_termination": true,
                "device_name": "/dev/sda1",
                "encrypted": false,
                "iops": 100,
                "kms_key_id": "",
                "volume_id": "vol-0ad20c7911350e5c0",
                "volume_size": 8,
                "volume_type": "gp2"
              }
            ],
            "security_groups": [],
            "source_dest_check": true,
            "subnet_id": "subnet-0d839e551d55605a2",
            "tags": null,
            "tenancy": "default",
            "timeouts": null,
            "user_data": null,
            "user_data_base64": null,
            "volume_tags": {},
            "vpc_security_group_ids": [
              "sg-06e8cc601eab204e5"
            ]
          },
          "private": "eyJlMmJmYjczMC1lY2FhLTExZTYtOGY4OC0zNDM2M2JjN2M0YzAiOnsiY3JlYXRlIjo2MDAwMDAwMDAwMDAsImRlbGV0ZSI6MTIwMDAwMDAwMDAwMCwidXBkYXRlIjo2MDAwMDAwMDAwMDB9LCJzY2hlbWFfdmVyc2lvbiI6IjEifQ==",
          "dependencies": [
            "aws_key_pair.mykey",
            "aws_security_group.allow-ssh",
            "aws_subnet.main-public-3"
          ]
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_internet_gateway",
      "name": "main-gw",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 0,
          "attributes": {
            "id": "igw-0c83f7bdb62175671",
            "owner_id": "431317591088",
            "tags": {
              "Name": "main"
            },
            "vpc_id": "vpc-0ddc396c0ff4b02ab"
          },
          "private": "bnVsbA==",
          "dependencies": [
            "aws_vpc.main"
          ]
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_key_pair",
      "name": "mykey",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 1,
          "attributes": {
            "fingerprint": "9b:4c:66:74:5e:e8:c9:82:87:29:3a:6e:e4:b2:2e:a3",
            "id": "mykey",
            "key_name": "mykey",
            "key_name_prefix": null,
            "key_pair_id": "key-0bd0bd5c927a86ce6",
            "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDLuODMkv29zQazQZCiOvFxKRgOZCELVi+RNdEdXxPS1kBB5yg0n+2Fjm+V6nb2rkQvVLV8RjqNXBbDKpnHHikZcqsIbXclIGbv/sUSe11aSceN3CXVAGl6xe0CetjhAMBUOCMLwyU1pzx82iEIFzCiyl0sCNUxQ5pX10SLowmTsTmt8A85YbH378KQ8zWLVqUv+MtC4ZeTU4tekmOg5hTnqHFlV1xtw1mgyC+9NDw+R6gcCigJDz7ly+VWfzK31yridgVAr7gU4p8iM5lkv0LNsga2V2231UZX+qWnQmx+IeLgJF0JXE7ZDLOSyIoHOH5VyiwptJBXUZRS3AWPMPZ9 ubuntu@u1",
            "tags": null
          },
          "private": "eyJzY2hlbWFfdmVyc2lvbiI6IjEifQ=="
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_route_table",
      "name": "main-public",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 0,
          "attributes": {
            "id": "rtb-056417eff78b9e96f",
            "owner_id": "431317591088",
            "propagating_vgws": [],
            "route": [
              {
                "cidr_block": "0.0.0.0/0",
                "egress_only_gateway_id": "",
                "gateway_id": "igw-0c83f7bdb62175671",
                "instance_id": "",
                "ipv6_cidr_block": "",
                "nat_gateway_id": "",
                "network_interface_id": "",
                "transit_gateway_id": "",
                "vpc_peering_connection_id": ""
              }
            ],
            "tags": {
              "Name": "main-public-1"
            },
            "vpc_id": "vpc-0ddc396c0ff4b02ab"
          },
          "private": "bnVsbA==",
          "dependencies": [
            "aws_internet_gateway.main-gw",
            "aws_vpc.main"
          ]
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_route_table_association",
      "name": "main-public-1-a",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 0,
          "attributes": {
            "gateway_id": null,
            "id": "rtbassoc-0be59876e8a2b5331",
            "route_table_id": "rtb-056417eff78b9e96f",
            "subnet_id": "subnet-03b119e5b8d9a8c2d"
          },
          "private": "bnVsbA==",
          "dependencies": [
            "aws_internet_gateway.main-gw",
            "aws_route_table.main-public",
            "aws_subnet.main-public-1",
            "aws_vpc.main"
          ]
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_route_table_association",
      "name": "main-public-2-a",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 0,
          "attributes": {
            "gateway_id": null,
            "id": "rtbassoc-071bf69778b837573",
            "route_table_id": "rtb-056417eff78b9e96f",
            "subnet_id": "subnet-07a5bb8a119ed0295"
          },
          "private": "bnVsbA==",
          "dependencies": [
            "aws_internet_gateway.main-gw",
            "aws_route_table.main-public",
            "aws_subnet.main-public-2",
            "aws_vpc.main"
          ]
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_route_table_association",
      "name": "main-public-3-a",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 0,
          "attributes": {
            "gateway_id": null,
            "id": "rtbassoc-066fb03bf0211ada5",
            "route_table_id": "rtb-056417eff78b9e96f",
            "subnet_id": "subnet-0d839e551d55605a2"
          },
          "private": "bnVsbA==",
          "dependencies": [
            "aws_internet_gateway.main-gw",
            "aws_route_table.main-public",
            "aws_subnet.main-public-3",
            "aws_vpc.main"
          ]
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_security_group",
      "name": "allow-ssh",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 1,
          "attributes": {
            "arn": "arn:aws:ec2:eu-west-1:431317591088:security-group/sg-06e8cc601eab204e5",
            "description": "security group that allows ssh and all egress traffic",
            "egress": [
              {
                "cidr_blocks": [
                  "0.0.0.0/0"
                ],
                "description": "",
                "from_port": 0,
                "ipv6_cidr_blocks": [],
                "prefix_list_ids": [],
                "protocol": "-1",
                "security_groups": [],
                "self": false,
                "to_port": 0
              }
            ],
            "id": "sg-06e8cc601eab204e5",
            "ingress": [
              {
                "cidr_blocks": [
                  "0.0.0.0/0"
                ],
                "description": "",
                "from_port": 22,
                "ipv6_cidr_blocks": [],
                "prefix_list_ids": [],
                "protocol": "tcp",
                "security_groups": [],
                "self": false,
                "to_port": 22
              }
            ],
            "name": "allow-ssh",
            "name_prefix": null,
            "owner_id": "431317591088",
            "revoke_rules_on_delete": false,
            "tags": {
              "Name": "allow-ssh"
            },
            "timeouts": null,
            "vpc_id": "vpc-0ddc396c0ff4b02ab"
          },
          "private": "eyJlMmJmYjczMC1lY2FhLTExZTYtOGY4OC0zNDM2M2JjN2M0YzAiOnsiY3JlYXRlIjo2MDAwMDAwMDAwMDAsImRlbGV0ZSI6NjAwMDAwMDAwMDAwfSwic2NoZW1hX3ZlcnNpb24iOiIxIn0=",
          "dependencies": [
            "aws_vpc.main"
          ]
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_subnet",
      "name": "main-private-1",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 1,
          "attributes": {
            "arn": "arn:aws:ec2:eu-west-1:431317591088:subnet/subnet-0e4e68a8fb5b7f932",
            "assign_ipv6_address_on_creation": false,
            "availability_zone": "eu-west-1a",
            "availability_zone_id": "euw1-az3",
            "cidr_block": "10.0.4.0/24",
            "id": "subnet-0e4e68a8fb5b7f932",
            "ipv6_cidr_block": "",
            "ipv6_cidr_block_association_id": "",
            "map_public_ip_on_launch": false,
            "outpost_arn": "",
            "owner_id": "431317591088",
            "tags": {
              "Name": "main-private-1"
            },
            "timeouts": null,
            "vpc_id": "vpc-0ddc396c0ff4b02ab"
          },
          "private": "eyJlMmJmYjczMC1lY2FhLTExZTYtOGY4OC0zNDM2M2JjN2M0YzAiOnsiY3JlYXRlIjo2MDAwMDAwMDAwMDAsImRlbGV0ZSI6MTIwMDAwMDAwMDAwMH0sInNjaGVtYV92ZXJzaW9uIjoiMSJ9",
          "dependencies": [
            "aws_vpc.main"
          ]
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_subnet",
      "name": "main-private-2",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 1,
          "attributes": {
            "arn": "arn:aws:ec2:eu-west-1:431317591088:subnet/subnet-03340a66d6fda6c04",
            "assign_ipv6_address_on_creation": false,
            "availability_zone": "eu-west-1b",
            "availability_zone_id": "euw1-az1",
            "cidr_block": "10.0.5.0/24",
            "id": "subnet-03340a66d6fda6c04",
            "ipv6_cidr_block": "",
            "ipv6_cidr_block_association_id": "",
            "map_public_ip_on_launch": false,
            "outpost_arn": "",
            "owner_id": "431317591088",
            "tags": {
              "Name": "main-private-2"
            },
            "timeouts": null,
            "vpc_id": "vpc-0ddc396c0ff4b02ab"
          },
          "private": "eyJlMmJmYjczMC1lY2FhLTExZTYtOGY4OC0zNDM2M2JjN2M0YzAiOnsiY3JlYXRlIjo2MDAwMDAwMDAwMDAsImRlbGV0ZSI6MTIwMDAwMDAwMDAwMH0sInNjaGVtYV92ZXJzaW9uIjoiMSJ9",
          "dependencies": [
            "aws_vpc.main"
          ]
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_subnet",
      "name": "main-private-3",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 1,
          "attributes": {
            "arn": "arn:aws:ec2:eu-west-1:431317591088:subnet/subnet-058492f5659aae5bd",
            "assign_ipv6_address_on_creation": false,
            "availability_zone": "eu-west-1c",
            "availability_zone_id": "euw1-az2",
            "cidr_block": "10.0.6.0/24",
            "id": "subnet-058492f5659aae5bd",
            "ipv6_cidr_block": "",
            "ipv6_cidr_block_association_id": "",
            "map_public_ip_on_launch": false,
            "outpost_arn": "",
            "owner_id": "431317591088",
            "tags": {
              "Name": "main-private-3"
            },
            "timeouts": null,
            "vpc_id": "vpc-0ddc396c0ff4b02ab"
          },
          "private": "eyJlMmJmYjczMC1lY2FhLTExZTYtOGY4OC0zNDM2M2JjN2M0YzAiOnsiY3JlYXRlIjo2MDAwMDAwMDAwMDAsImRlbGV0ZSI6MTIwMDAwMDAwMDAwMH0sInNjaGVtYV92ZXJzaW9uIjoiMSJ9",
          "dependencies": [
            "aws_vpc.main"
          ]
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_subnet",
      "name": "main-public-1",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 1,
          "attributes": {
            "arn": "arn:aws:ec2:eu-west-1:431317591088:subnet/subnet-03b119e5b8d9a8c2d",
            "assign_ipv6_address_on_creation": false,
            "availability_zone": "eu-west-1a",
            "availability_zone_id": "euw1-az3",
            "cidr_block": "10.0.1.0/24",
            "id": "subnet-03b119e5b8d9a8c2d",
            "ipv6_cidr_block": "",
            "ipv6_cidr_block_association_id": "",
            "map_public_ip_on_launch": true,
            "outpost_arn": "",
            "owner_id": "431317591088",
            "tags": {
              "Name": "main-public-1"
            },
            "timeouts": null,
            "vpc_id": "vpc-0ddc396c0ff4b02ab"
          },
          "private": "eyJlMmJmYjczMC1lY2FhLTExZTYtOGY4OC0zNDM2M2JjN2M0YzAiOnsiY3JlYXRlIjo2MDAwMDAwMDAwMDAsImRlbGV0ZSI6MTIwMDAwMDAwMDAwMH0sInNjaGVtYV92ZXJzaW9uIjoiMSJ9",
          "dependencies": [
            "aws_vpc.main"
          ]
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_subnet",
      "name": "main-public-2",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 1,
          "attributes": {
            "arn": "arn:aws:ec2:eu-west-1:431317591088:subnet/subnet-07a5bb8a119ed0295",
            "assign_ipv6_address_on_creation": false,
            "availability_zone": "eu-west-1b",
            "availability_zone_id": "euw1-az1",
            "cidr_block": "10.0.2.0/24",
            "id": "subnet-07a5bb8a119ed0295",
            "ipv6_cidr_block": "",
            "ipv6_cidr_block_association_id": "",
            "map_public_ip_on_launch": true,
            "outpost_arn": "",
            "owner_id": "431317591088",
            "tags": {
              "Name": "main-public-2"
            },
            "timeouts": null,
            "vpc_id": "vpc-0ddc396c0ff4b02ab"
          },
          "private": "eyJlMmJmYjczMC1lY2FhLTExZTYtOGY4OC0zNDM2M2JjN2M0YzAiOnsiY3JlYXRlIjo2MDAwMDAwMDAwMDAsImRlbGV0ZSI6MTIwMDAwMDAwMDAwMH0sInNjaGVtYV92ZXJzaW9uIjoiMSJ9",
          "dependencies": [
            "aws_vpc.main"
          ]
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_subnet",
      "name": "main-public-3",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 1,
          "attributes": {
            "arn": "arn:aws:ec2:eu-west-1:431317591088:subnet/subnet-0d839e551d55605a2",
            "assign_ipv6_address_on_creation": false,
            "availability_zone": "eu-west-1c",
            "availability_zone_id": "euw1-az2",
            "cidr_block": "10.0.3.0/24",
            "id": "subnet-0d839e551d55605a2",
            "ipv6_cidr_block": "",
            "ipv6_cidr_block_association_id": "",
            "map_public_ip_on_launch": true,
            "outpost_arn": "",
            "owner_id": "431317591088",
            "tags": {
              "Name": "main-public-3"
            },
            "timeouts": null,
            "vpc_id": "vpc-0ddc396c0ff4b02ab"
          },
          "private": "eyJlMmJmYjczMC1lY2FhLTExZTYtOGY4OC0zNDM2M2JjN2M0YzAiOnsiY3JlYXRlIjo2MDAwMDAwMDAwMDAsImRlbGV0ZSI6MTIwMDAwMDAwMDAwMH0sInNjaGVtYV92ZXJzaW9uIjoiMSJ9",
          "dependencies": [
            "aws_vpc.main"
          ]
        }
      ]
    },
    {
      "mode": "managed",
      "type": "aws_vpc",
      "name": "main",
      "provider": "provider.aws",
      "instances": [
        {
          "schema_version": 1,
          "attributes": {
            "arn": "arn:aws:ec2:eu-west-1:431317591088:vpc/vpc-0ddc396c0ff4b02ab",
            "assign_generated_ipv6_cidr_block": false,
            "cidr_block": "10.0.0.0/16",
            "default_network_acl_id": "acl-0c9377c58c531a713",
            "default_route_table_id": "rtb-076b454cd91cb20b8",
            "default_security_group_id": "sg-094ad28138d5e1e61",
            "dhcp_options_id": "dopt-0d28e5e520dbf958e",
            "enable_classiclink": false,
            "enable_classiclink_dns_support": false,
            "enable_dns_hostnames": true,
            "enable_dns_support": true,
            "id": "vpc-0ddc396c0ff4b02ab",
            "instance_tenancy": "default",
            "ipv6_association_id": "",
            "ipv6_cidr_block": "",
            "main_route_table_id": "rtb-076b454cd91cb20b8",
            "owner_id": "431317591088",
            "tags": {
              "Name": "main"
            }
          },
          "private": "eyJzY2hlbWFfdmVyc2lvbiI6IjEifQ=="
        }
      ]
    }
  ]
}


```


## 삭제
```
ubuntu@u1:/mnt/hgfs/Desktop/terraform_ex/sol3$ terraform destroy -auto-approve
aws_vpc.main: Refreshing state... [id=vpc-0ddc396c0ff4b02ab]
aws_key_pair.mykey: Refreshing state... [id=mykey]
aws_security_group.allow-ssh: Refreshing state... [id=sg-06e8cc601eab204e5]
aws_subnet.main-private-2: Refreshing state... [id=subnet-03340a66d6fda6c04]
aws_subnet.main-public-3: Refreshing state... [id=subnet-0d839e551d55605a2]
aws_subnet.main-private-3: Refreshing state... [id=subnet-058492f5659aae5bd]
aws_internet_gateway.main-gw: Refreshing state... [id=igw-0c83f7bdb62175671]
aws_subnet.main-public-1: Refreshing state... [id=subnet-03b119e5b8d9a8c2d]
aws_subnet.main-private-1: Refreshing state... [id=subnet-0e4e68a8fb5b7f932]
aws_subnet.main-public-2: Refreshing state... [id=subnet-07a5bb8a119ed0295]
aws_instance.example3: Refreshing state... [id=i-0c069f40f2086e5f2]
aws_instance.example2: Refreshing state... [id=i-009946c58b19b18f6]
aws_instance.example1: Refreshing state... [id=i-01531d36f75e02c62]
aws_route_table.main-public: Refreshing state... [id=rtb-056417eff78b9e96f]
aws_route_table_association.main-public-2-a: Refreshing state... [id=rtbassoc-071bf69778b837573]
aws_route_table_association.main-public-1-a: Refreshing state... [id=rtbassoc-0be59876e8a2b5331]
aws_route_table_association.main-public-3-a: Refreshing state... [id=rtbassoc-066fb03bf0211ada5]
aws_route_table_association.main-public-3-a: Destroying... [id=rtbassoc-066fb03bf0211ada5]
aws_route_table_association.main-public-1-a: Destroying... [id=rtbassoc-0be59876e8a2b5331]
aws_subnet.main-private-2: Destroying... [id=subnet-03340a66d6fda6c04]
aws_subnet.main-private-3: Destroying... [id=subnet-058492f5659aae5bd]
aws_instance.example3: Destroying... [id=i-0c069f40f2086e5f2]
aws_instance.example1: Destroying... [id=i-01531d36f75e02c62]
aws_subnet.main-private-1: Destroying... [id=subnet-0e4e68a8fb5b7f932]
aws_route_table_association.main-public-2-a: Destroying... [id=rtbassoc-071bf69778b837573]
aws_instance.example2: Destroying... [id=i-009946c58b19b18f6]
aws_route_table_association.main-public-1-a: Destruction complete after 1s
aws_route_table_association.main-public-2-a: Destruction complete after 1s
aws_route_table_association.main-public-3-a: Destruction complete after 1s
aws_route_table.main-public: Destroying... [id=rtb-056417eff78b9e96f]
aws_subnet.main-private-1: Destruction complete after 3s
aws_subnet.main-private-2: Destruction complete after 3s
aws_subnet.main-private-3: Destruction complete after 3s
aws_route_table.main-public: Destruction complete after 5s
aws_internet_gateway.main-gw: Destroying... [id=igw-0c83f7bdb62175671]
aws_instance.example3: Still destroying... [id=i-0c069f40f2086e5f2, 10s elapsed]
aws_instance.example1: Still destroying... [id=i-01531d36f75e02c62, 10s elapsed]
aws_instance.example2: Still destroying... [id=i-009946c58b19b18f6, 10s elapsed]
aws_internet_gateway.main-gw: Still destroying... [id=igw-0c83f7bdb62175671, 10s elapsed]
aws_instance.example1: Still destroying... [id=i-01531d36f75e02c62, 20s elapsed]
aws_instance.example3: Still destroying... [id=i-0c069f40f2086e5f2, 20s elapsed]
aws_instance.example2: Still destroying... [id=i-009946c58b19b18f6, 20s elapsed]
aws_instance.example1: Destruction complete after 26s
aws_subnet.main-public-1: Destroying... [id=subnet-03b119e5b8d9a8c2d]
aws_instance.example2: Destruction complete after 26s
aws_subnet.main-public-2: Destroying... [id=subnet-07a5bb8a119ed0295]
aws_internet_gateway.main-gw: Still destroying... [id=igw-0c83f7bdb62175671, 20s elapsed]
aws_internet_gateway.main-gw: Destruction complete after 23s
aws_subnet.main-public-1: Destruction complete after 3s
aws_instance.example3: Still destroying... [id=i-0c069f40f2086e5f2, 30s elapsed]
aws_subnet.main-public-2: Destruction complete after 4s
aws_instance.example3: Destruction complete after 38s
aws_key_pair.mykey: Destroying... [id=mykey]
aws_subnet.main-public-3: Destroying... [id=subnet-0d839e551d55605a2]
aws_security_group.allow-ssh: Destroying... [id=sg-06e8cc601eab204e5]
aws_key_pair.mykey: Destruction complete after 2s
aws_subnet.main-public-3: Destruction complete after 4s
aws_security_group.allow-ssh: Destruction complete after 4s
aws_vpc.main: Destroying... [id=vpc-0ddc396c0ff4b02ab]
aws_vpc.main: Destruction complete after 2s

Destroy complete! Resources: 17 destroyed.

```
