FirstEC2
--------------

# Terraform Settings Block
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      #version = "~> 3.21" # Optional but recommended in production
    }
  }
}

# Provider Block
provider "aws" {
  profile = "default" # AWS Credentials Profile configured on your local desktop terminal  $HOME/.aws/credentials
  region  = "ap-southeast-1"
}

# Resource Block
resource "aws_instance" "myec2" {
  ami           = "ami-0ff89c4ce7de192ea" # Amazon Linux in -1, update as per your region
  instance_type = "t2.micro"
}


------------github repo-----
terraform {
  required_providers {
    github = {
      source = "integrations/github"
      version = "4.28.0"
    }
  }
}


# Configure the GitHub Provider
provider "github" {
  token = "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"
}

resource "github_repository" "example" {
  name        = "terraform-repo"
  visibility  = "public"

}
