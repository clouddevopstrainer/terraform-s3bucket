# terraform-s3bucket
terraform-s3bucket
hp@DESKTOP-E1BV25S MINGW64 ~/OneDrive/Desktop/s3-terraform (main)
$ ls

hp@DESKTOP-E1BV25S MINGW64 ~/OneDrive/Desktop/s3-terraform (main)
$ git init
Initialized empty Git repository in C:/Users/hp/OneDrive/Desktop/s3-terraform/.git/

hp@DESKTOP-E1BV25S MINGW64 ~/OneDrive/Desktop/s3-terraform (main)
$ git clone https://github.com/clouddevopstrainer/terraform-s3bucket.git
Cloning into 'terraform-s3bucket'...
remote: Enumerating objects: 15, done.
remote: Counting objects: 100% (15/15), done.
remote: Compressing objects: 100% (13/13), done.
remote: Total 15 (delta 3), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (15/15), 4.77 KiB | 444.00 KiB/s, done.
Resolving deltas: 100% (3/3), done.

hp@DESKTOP-E1BV25S MINGW64 ~/OneDrive/Desktop/s3-terraform (main)
$ ls
terraform-s3bucket/

hp@DESKTOP-E1BV25S MINGW64 ~/OneDrive/Desktop/s3-terraform (main)
$ cd terraform-s3bucket/

hp@DESKTOP-E1BV25S MINGW64 ~/OneDrive/Desktop/s3-terraform/terraform-s3bucket (main)
$ ls
main.tf  README.md  terraform.tfvars  variables.tf

hp@DESKTOP-E1BV25S MINGW64 ~/OneDrive/Desktop/s3-terraform/terraform-s3bucket (main)
$ terraform init
Initializing the backend...
Initializing provider plugins...
- Finding hashicorp/aws versions matching "~> 5.0"...
- Installing hashicorp/aws v5.93.0...
- Installed hashicorp/aws v5.93.0 (signed by HashiCorp)
Terraform has created a lock file .terraform.lock.hcl to record the provider
selections it made above. Include this file in your version control repository
so that Terraform can guarantee to make the same selections by default when
you run "terraform init" in the future.

Terraform has been successfully initialized!

You may now begin working with Terraform. Try running "terraform plan" to see
any changes that are required for your infrastructure. All Terraform commands
should now work.

If you ever set or change modules or backend configuration for Terraform,
rerun this command to reinitialize your working directory. If you forget, other
commands will detect it and remind you to do so if necessary.

hp@DESKTOP-E1BV25S MINGW64 ~/OneDrive/Desktop/s3-terraform/terraform-s3bucket (main)
$ terraform validate
╷
│ Warning: Argument is deprecated
│
│   with aws_s3_bucket.my_bucket,
│   on main.tf line 17, in resource "aws_s3_bucket" "my_bucket":
│   17:   acl    = "private"
│
│ acl is deprecated. Use the aws_s3_bucket_acl resource instead.
╵
Success! The configuration is valid, but there were some validation warnings as
shown above.


hp@DESKTOP-E1BV25S MINGW64 ~/OneDrive/Desktop/s3-terraform/terraform-s3bucket (main)
$ terraform plan

Terraform used the selected providers to generate the following execution plan. Resource      
actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:

  # aws_s3_bucket.my_bucket will be created
  + resource "aws_s3_bucket" "my_bucket" {
      + acceleration_status         = (known after apply)
      + acl                         = "private"
      + arn                         = (known after apply)
      + bucket                      = "my-unique-bucket-name-new"
      + bucket_domain_name          = (known after apply)
      + bucket_prefix               = (known after apply)
      + bucket_regional_domain_name = (known after apply)
      + force_destroy               = false
      + hosted_zone_id              = (known after apply)
      + id                          = (known after apply)
      + object_lock_enabled         = (known after apply)
      + policy                      = (known after apply)
      + region                      = (known after apply)
      + request_payer               = (known after apply)
      + tags_all                    = (known after apply)
      + website_domain              = (known after apply)
      + website_endpoint            = (known after apply)

      + cors_rule (known after apply)

      + grant (known after apply)

      + lifecycle_rule (known after apply)

      + logging (known after apply)

      + object_lock_configuration (known after apply)

      + replication_configuration (known after apply)

      + server_side_encryption_configuration (known after apply)

      + versioning (known after apply)

      + website (known after apply)
    }

Plan: 1 to add, 0 to change, 0 to destroy.
╷
│ Warning: Argument is deprecated
│
│   with aws_s3_bucket.my_bucket,
│   on main.tf line 17, in resource "aws_s3_bucket" "my_bucket":
│   17:   acl    = "private"
│
│ acl is deprecated. Use the aws_s3_bucket_acl resource instead.
│
│ (and one more similar warning elsewhere)
╵

───────────────────────────────────────────────────────────────────────────────────────────── 

Note: You didn't use the -out option to save this plan, so Terraform can't guarantee to take  
exactly these actions if you run "terraform apply" now.

hp@DESKTOP-E1BV25S MINGW64 ~/OneDrive/Desktop/s3-terraform/terraform-s3bucket (main)
$ terraform apply -auto-approve

Terraform used the selected providers to generate the following execution plan. Resource      
actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:

  # aws_s3_bucket.my_bucket will be created
  + resource "aws_s3_bucket" "my_bucket" {
      + acceleration_status         = (known after apply)
      + acl                         = "private"
      + arn                         = (known after apply)
      + bucket                      = "my-unique-bucket-name-new"
      + bucket_domain_name          = (known after apply)
      + bucket_prefix               = (known after apply)
      + bucket_regional_domain_name = (known after apply)
      + force_destroy               = false
      + hosted_zone_id              = (known after apply)
      + id                          = (known after apply)
      + object_lock_enabled         = (known after apply)
      + policy                      = (known after apply)
      + region                      = (known after apply)
      + request_payer               = (known after apply)
      + tags_all                    = (known after apply)
      + website_domain              = (known after apply)
      + website_endpoint            = (known after apply)

      + cors_rule (known after apply)

      + grant (known after apply)

      + lifecycle_rule (known after apply)

      + logging (known after apply)

      + object_lock_configuration (known after apply)

      + replication_configuration (known after apply)

      + server_side_encryption_configuration (known after apply)

      + versioning (known after apply)

      + website (known after apply)
    }

Plan: 1 to add, 0 to change, 0 to destroy.
aws_s3_bucket.my_bucket: Creating...
╷
│ Warning: Argument is deprecated
│
│   with aws_s3_bucket.my_bucket,
│   on main.tf line 17, in resource "aws_s3_bucket" "my_bucket":
│   17:   acl    = "private"
│
│ acl is deprecated. Use the aws_s3_bucket_acl resource instead.
│
│ (and 2 more similar warnings elsewhere)
╵
╷
│ Error: creating S3 Bucket (my-unique-bucket-name-new): operation error S3: CreateBucket, https response error StatusCode: 409, RequestID: EN1VG4C47873H906, HostID: EZ6Z9O73IX1/FFLAgiO632VtbctVc8d+nRI9rEHyAoYuolr92vqEEY9Z/NQ0CuTRIkmHrUNeLjY=, BucketAlreadyExists: 
│
│   with aws_s3_bucket.my_bucket,
│   on main.tf line 15, in resource "aws_s3_bucket" "my_bucket":
│   15: resource "aws_s3_bucket" "my_bucket" {
│
╵

hp@DESKTOP-E1BV25S MINGW64 ~/OneDrive/Desktop/s3-terraform/terraform-s3bucket (main)
$ terraform plan

Terraform used the selected providers to generate the following execution plan. Resource      
actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:

  # aws_s3_bucket.my_bucket will be created
  + resource "aws_s3_bucket" "my_bucket" {
      + acceleration_status         = (known after apply)
      + acl                         = "private"
      + arn                         = (known after apply)
      + bucket                      = "my-unique-bucket-name-newapr"
      + bucket_domain_name          = (known after apply)
      + bucket_prefix               = (known after apply)
      + bucket_regional_domain_name = (known after apply)
      + force_destroy               = false
      + hosted_zone_id              = (known after apply)
      + id                          = (known after apply)
      + object_lock_enabled         = (known after apply)
      + policy                      = (known after apply)
      + region                      = (known after apply)
      + request_payer               = (known after apply)
      + tags_all                    = (known after apply)
      + website_domain              = (known after apply)
      + website_endpoint            = (known after apply)

      + cors_rule (known after apply)

      + grant (known after apply)

      + lifecycle_rule (known after apply)

      + logging (known after apply)

      + object_lock_configuration (known after apply)

      + replication_configuration (known after apply)

      + server_side_encryption_configuration (known after apply)

      + versioning (known after apply)

      + website (known after apply)
    }

Plan: 1 to add, 0 to change, 0 to destroy.
╷
│ Warning: Argument is deprecated
│
│   with aws_s3_bucket.my_bucket,
│   on main.tf line 17, in resource "aws_s3_bucket" "my_bucket":
│   17:   acl    = "private"
│
│ acl is deprecated. Use the aws_s3_bucket_acl resource instead.
│
│ (and one more similar warning elsewhere)
╵

───────────────────────────────────────────────────────────────────────────────────────────── 

Note: You didn't use the -out option to save this plan, so Terraform can't guarantee to take  
exactly these actions if you run "terraform apply" now.

hp@DESKTOP-E1BV25S MINGW64 ~/OneDrive/Desktop/s3-terraform/terraform-s3bucket (main)
$ terraform apply

Terraform used the selected providers to generate the following execution plan. Resource      
actions are indicated with the following symbols:
  + create

Terraform will perform the following actions:

  # aws_s3_bucket.my_bucket will be created
  + resource "aws_s3_bucket" "my_bucket" {
      + acceleration_status         = (known after apply)
      + acl                         = "private"
      + arn                         = (known after apply)
      + bucket                      = "my-unique-bucket-name-newapr"
      + bucket_domain_name          = (known after apply)
      + bucket_prefix               = (known after apply)
      + bucket_regional_domain_name = (known after apply)
      + force_destroy               = false
      + hosted_zone_id              = (known after apply)
      + id                          = (known after apply)
      + object_lock_enabled         = (known after apply)
      + policy                      = (known after apply)
      + region                      = (known after apply)
      + request_payer               = (known after apply)
      + tags_all                    = (known after apply)
      + website_domain              = (known after apply)
      + website_endpoint            = (known after apply)

      + cors_rule (known after apply)

      + grant (known after apply)

      + lifecycle_rule (known after apply)

      + logging (known after apply)

      + object_lock_configuration (known after apply)

      + replication_configuration (known after apply)

      + server_side_encryption_configuration (known after apply)

      + versioning (known after apply)

      + website (known after apply)
    }

Plan: 1 to add, 0 to change, 0 to destroy.
╷
│ Warning: Argument is deprecated
│
│   with aws_s3_bucket.my_bucket,
│   on main.tf line 17, in resource "aws_s3_bucket" "my_bucket":
│   17:   acl    = "private"
│
│ acl is deprecated. Use the aws_s3_bucket_acl resource instead.
│
│ (and one more similar warning elsewhere)
╵

Do you want to perform these actions?
  Terraform will perform the actions described above.
  Only 'yes' will be accepted to approve.

  Enter a value: yes

aws_s3_bucket.my_bucket: Creating...
aws_s3_bucket.my_bucket: Creation complete after 6s [id=my-unique-bucket-name-newapr]
╷
│ Warning: Argument is deprecated
│
│   with aws_s3_bucket.my_bucket,
│   on main.tf line 17, in resource "aws_s3_bucket" "my_bucket":
│   17:   acl    = "private"
│
│ acl is deprecated. Use the aws_s3_bucket_acl resource instead.
╵

Apply complete! Resources: 1 added, 0 changed, 0 destroyed.

hp@DESKTOP-E1BV25S MINGW64 ~/OneDrive/Desktop/s3-terraform/terraform-s3bucket (main)
$ terraform destroy
aws_s3_bucket.my_bucket: Refreshing state... [id=my-unique-bucket-name-newapr]

Terraform used the selected providers to generate the following execution plan. Resource      
actions are indicated with the following symbols:
  - destroy

Terraform will perform the following actions:

  # aws_s3_bucket.my_bucket will be destroyed
  - resource "aws_s3_bucket" "my_bucket" {
      - acl                         = "private" -> null
      - arn                         = "arn:aws:s3:::my-unique-bucket-name-newapr" -> null     
      - bucket                      = "my-unique-bucket-name-newapr" -> null
      - bucket_domain_name          = "my-unique-bucket-name-newapr.s3.amazonaws.com" -> null 
      - bucket_regional_domain_name = "my-unique-bucket-name-newapr.s3.us-east-1.amazonaws.com" -> null
      - force_destroy               = false -> null
      - hosted_zone_id              = "Z3AQBSTGFYJSTF" -> null
      - id                          = "my-unique-bucket-name-newapr" -> null
      - object_lock_enabled         = false -> null
      - region                      = "us-east-1" -> null
      - request_payer               = "BucketOwner" -> null
      - tags                        = {} -> null
      - tags_all                    = {} -> null
        # (3 unchanged attributes hidden)

      - grant {
          - id          = "b6f0ec53eda0b48acde195968f5c5dd9e298c8d852036068bae83354206bd35c" -> null
          - permissions = [
              - "FULL_CONTROL",
            ] -> null
          - type        = "CanonicalUser" -> null
            # (1 unchanged attribute hidden)
        }

      - server_side_encryption_configuration {
          - rule {
              - bucket_key_enabled = false -> null

              - apply_server_side_encryption_by_default {
                  - sse_algorithm     = "AES256" -> null
                    # (1 unchanged attribute hidden)
                }
            }
        }

      - versioning {
          - enabled    = false -> null
          - mfa_delete = false -> null
        }
    }

Plan: 0 to add, 0 to change, 1 to destroy.
╷
│ Warning: Argument is deprecated
│
│   with aws_s3_bucket.my_bucket,
│   on main.tf line 17, in resource "aws_s3_bucket" "my_bucket":
│   17:   acl    = "private"
│
│ acl is deprecated. Use the aws_s3_bucket_acl resource instead.
╵

Do you really want to destroy all resources?
  Terraform will destroy all your managed infrastructure, as shown above.
  There is no undo. Only 'yes' will be accepted to confirm.

  Enter a value: yes

aws_s3_bucket.my_bucket: Destroying... [id=my-unique-bucket-name-newapr]
aws_s3_bucket.my_bucket: Destruction complete after 1s

Destroy complete! Resources: 1 destroyed.

////////////////////
