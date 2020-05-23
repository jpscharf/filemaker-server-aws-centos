# FileMaker CentOS AMI #

# Requirements #
- [packer](https://packer.io)
- AWS KEYS

# Defaults #
- OS: `CentOS 7`
- Region: `us-east-2`
- Instance Type: `t3.small`
- Volumes:
    - `8GB EBS Boot`
    - `20GB EBS FileMaker Data`

# Building AMI Image #
1. Open `packer.json`
2. Verify the following variables: `filemaker_server_version` and `filemaker_server_download`
3. Make any desired changes to the `region`, `aws_instance_type`, or `filemaker_data_volume_size`
4. Save your changes.
5. Export your AWS Credentials
    - `export AWS_ACCESS_KEY_ID="<YOUR AWS KEY>`
    - `export AWS_SECRET_ACCESS_KEY="<YOUR AWS SECRET KEY>"`
6. Validate your changes `packer validate packer.json`
7. Build your AMI `packer build packer.json`
