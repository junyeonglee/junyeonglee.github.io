# AWS

## Installation

```sh
sudo apt update # Update package list
sudo apt install pip3-python # Skip if you've installed pip3

pip3 install awscli --upgrade --user # Install AWS CLI
aws configure --profile my-profile # Configure AWS Profile
```

## Example of simple `~/.aws/config`

```properties
[profile my-profile]
region = eu-west-1
output = json
mfa_serial = arn:aws:iam::my-aws-account-id:mfa/my-email-address
```

## Example of `~/.aws/credentials`

```properties
[my-profile]
aws_access_key_id = eu-west-1
aws_secret_access_key = json
source_profile = my-profile
```
