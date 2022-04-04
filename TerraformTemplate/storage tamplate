variable "storage_account_name" {
    type=string
    default="pnkstorage1234"
}

variable "resource_group_name" {
    type=string
    default="pnkRG"
}

provider "azurerm"{
version = "=2.0.0"
subscription_id = "4abe0d85-2544-4982-8eff-0de8b67e2b5c"
tenant_id       = "d95e1fad-1598-4269-85e3-3788fb3c8b88"
features {}
}

resource "azurerm_resource_group" "grp" {
  name     = var.resource_group_name
  location = "East US"
}

resource "azurerm_storage_account" "store" {
  name                     = var.storage_account_name
  resource_group_name      = azurerm_resource_group.grp.name
  location                 = azurerm_resource_group.grp.location
  account_tier             = "Standard"
  account_replication_type = "LRS"
}
