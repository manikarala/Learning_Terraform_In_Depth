

### data-source-03.tf

```sh
  provider "aws" {
  }
  
  # 3. Data Source: aws_iam_policy_document
  data "aws_iam_policy_document" "example" {
    statement {
      sid = "1"
  
      actions = [
        "s3:ListAllMyBuckets",
        "s3:GetBucketLocation",
      ]
  
      resources = [
        "arn:aws:s3:::*",
      ]
    }
  }
  
  resource "aws_iam_policy" "example" {
    name   = "example_policy"
    path   = "/"
    policy = data.aws_iam_policy_document.example.json
  }

```
