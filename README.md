# terraform-backend-setup-scripts
## Description
Build Terraform backend without using Terraform.

https://www.terraform.io/docs/backends/types/s3.html
> Terraform is an administrative tool that manages your infrastructure, and so ideally the infrastructure that is used by Terraform should exist outside of the infrastructure that Terraform manages. This can be achieved by creating a separate administrative AWS account which contains the user accounts used by human operators and any infrastructure and tools used to manage the other accounts. Isolating shared administrative tools from your main environments has a number of advantages, such as avoiding accidentally damaging the administrative infrastructure while changing the target infrastructure, and reducing the risk that an attacker might abuse production infrastructure to gain access to the (usually more privileged) administrative infrastructure.

## Usage
1. Run init.sh

    ```sh
    bash init.sh <STACK_NAME> <S3_BUCKET_NAME> <DYNAMODB_TABLE_NAME>
    ```

1. terraform init

    ```sh
    terraform init \
      -backend-config="bucket=<S3_BUCKET_NAME>" \
      -backend-config="dynamodb_table=<DYNAMODB_TABLE_NAME>"
    ```

### When removing the Terraform backend

  ```sh
  aws cloudformation delete-stack --stack-name <STACK_NAME>
  ```
