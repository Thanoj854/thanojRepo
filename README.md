terraform {
  required_providers {
    azurerm = {
      source  = "hashicorp/azurerm"
      version = "~> 3.0"
    }
  }
}
 
provider "azurerm" {
  features = {}
  # If you prefer, you can optionally set subscription_id here:
  # subscription_id = var.subscription_id
}
 
resource "azurerm_resource_group" "rg" {
  name     = "rg-terraform-demo"
  location = "eastus"
  tags = {
    environment = "demo"
    created_by  = "terraform"
  }
}
