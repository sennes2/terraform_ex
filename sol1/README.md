# terraform_ex sol1

## Result : timeout 발생했습니다. (서울, 도쿄 모두) 인스턴스 생성되었으나 ssh 접속 안되었습니다.
```
ubuntu@u1:/mnt/hgfs/Desktop/terraform_ex/sol1$ terraform init

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
ubuntu@u1:/mnt/hgfs/Desktop/terraform_ex/sol1$ terraform apply -auto-approve
aws_key_pair.mykey: Refreshing state... [id=mykey]
aws_instance.example: Refreshing state... [id=i-000299526b57e1589]
aws_instance.example: Destroying... [id=i-000299526b57e1589]
aws_instance.example: Still destroying... [id=i-000299526b57e1589, 10s elapsed]
aws_instance.example: Still destroying... [id=i-000299526b57e1589, 20s elapsed]
aws_instance.example: Still destroying... [id=i-000299526b57e1589, 30s elapsed]
aws_instance.example: Destruction complete after 31s
aws_instance.example: Creating...
aws_instance.example: Still creating... [10s elapsed]
aws_instance.example: Still creating... [20s elapsed]
aws_instance.example: Provisioning with 'file'...
aws_instance.example: Still creating... [30s elapsed]
aws_instance.example: Still creating... [40s elapsed]
aws_instance.example: Still creating... [50s elapsed]
aws_instance.example: Still creating... [1m0s elapsed]
aws_instance.example: Still creating... [1m10s elapsed]
aws_instance.example: Still creating... [1m20s elapsed]
aws_instance.example: Still creating... [1m30s elapsed]
aws_instance.example: Still creating... [1m40s elapsed]
aws_instance.example: Still creating... [1m50s elapsed]
aws_instance.example: Still creating... [2m0s elapsed]
aws_instance.example: Still creating... [2m10s elapsed]
aws_instance.example: Still creating... [2m20s elapsed]
aws_instance.example: Still creating... [2m30s elapsed]
aws_instance.example: Still creating... [2m40s elapsed]
aws_instance.example: Still creating... [2m50s elapsed]
aws_instance.example: Still creating... [3m0s elapsed]
aws_instance.example: Still creating... [3m10s elapsed]
aws_instance.example: Still creating... [3m20s elapsed]
aws_instance.example: Still creating... [3m30s elapsed]
aws_instance.example: Still creating... [3m40s elapsed]
aws_instance.example: Still creating... [3m50s elapsed]
aws_instance.example: Still creating... [4m0s elapsed]
aws_instance.example: Still creating... [4m10s elapsed]
aws_instance.example: Still creating... [4m20s elapsed]
aws_instance.example: Still creating... [4m30s elapsed]
aws_instance.example: Still creating... [4m40s elapsed]
aws_instance.example: Still creating... [4m50s elapsed]
aws_instance.example: Still creating... [5m0s elapsed]
aws_instance.example: Still creating... [5m10s elapsed]
aws_instance.example: Still creating... [5m20s elapsed]


Error: timeout - last error: dial tcp 52.198.246.132:22: i/o timeout





```

## tfstate
```
{
  "version": 4,
  "terraform_version": "0.12.24",
  "serial": 27,
  "lineage": "0c75f5cb-b1c7-f53d-1078-77f90802f015",
  "outputs": {},
  "resources": [
    {
      "mode": "managed",
      "type": "aws_instance",
      "name": "example",
      "provider": "provider.aws",
      "instances": [
        {
          "status": "tainted",
          "schema_version": 1,
          "attributes": {
            "ami": "ami-0278fe6949f6b1a06",
            "arn": "arn:aws:ec2:ap-northeast-1:431317591088:instance/i-081b6d0d06d6c30bf",
            "associate_public_ip_address": true,
            "availability_zone": "ap-northeast-1a",
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
            "id": "i-081b6d0d06d6c30bf",
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
            "primary_network_interface_id": "eni-004ee1ae82323bf92",
            "private_dns": "ip-172-31-43-151.ap-northeast-1.compute.internal",
            "private_ip": "172.31.43.151",
            "public_dns": "ec2-13-231-142-246.ap-northeast-1.compute.amazonaws.com",
            "public_ip": "13.231.142.246",
            "root_block_device": [
              {
                "delete_on_termination": true,
                "device_name": "/dev/sda1",
                "encrypted": false,
                "iops": 100,
                "kms_key_id": "",
                "volume_id": "vol-059c3a8f25f5de5e3",
                "volume_size": 8,
                "volume_type": "gp2"
              }
            ],
            "security_groups": [
              "default"
            ],
            "source_dest_check": true,
            "subnet_id": "subnet-0f302ff2f7af3d8dc",
            "tags": null,
            "tenancy": "default",
            "timeouts": null,
            "user_data": null,
            "user_data_base64": null,
            "volume_tags": {},
            "vpc_security_group_ids": [
              "sg-0507648dd526d8a0f"
            ]
          },
          "private": "eyJlMmJmYjczMC1lY2FhLTExZTYtOGY4OC0zNDM2M2JjN2M0YzAiOnsiY3JlYXRlIjo2MDAwMDAwMDAwMDAsImRlbGV0ZSI6MTIwMDAwMDAwMDAwMCwidXBkYXRlIjo2MDAwMDAwMDAwMDB9LCJzY2hlbWFfdmVyc2lvbiI6IjEifQ==",
          "dependencies": [
            "aws_key_pair.mykey"
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
            "key_pair_id": "key-05accebd39b281739",
            "public_key": "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDLuODMkv29zQazQZCiOvFxKRgOZCELVi+RNdEdXxPS1kBB5yg0n+2Fjm+V6nb2rkQvVLV8RjqNXBbDKpnHHikZcqsIbXclIGbv/sUSe11aSceN3CXVAGl6xe0CetjhAMBUOCMLwyU1pzx82iEIFzCiyl0sCNUxQ5pX10SLowmTsTmt8A85YbH378KQ8zWLVqUv+MtC4ZeTU4tekmOg5hTnqHFlV1xtw1mgyC+9NDw+R6gcCigJDz7ly+VWfzK31yridgVAr7gU4p8iM5lkv0LNsga2V2231UZX+qWnQmx+IeLgJF0JXE7ZDLOSyIoHOH5VyiwptJBXUZRS3AWPMPZ9 ubuntu@u1",
            "tags": {}
          },
          "private": "eyJzY2hlbWFfdmVyc2lvbiI6IjEifQ=="
        }
      ]
    }
  ]
}

```
