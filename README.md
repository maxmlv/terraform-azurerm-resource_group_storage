# terraform-azurerm-resource_group_storage

A small Terraform module that provisions an Azure Resource Group and a Storage Account within it.

## Usage

```hcl
module "storage" {
  source = "github.com/maxmlv/terraform-azurerm-storage-account"

  resource_group_name  = "my-resource-group"
  storage_account_name = "mystorageaccount123"
  location              = "westeurope"
}
```

## Requirements

| Name | Version |
|------|---------|
| terraform | >= 1.0 |
| azurerm | >= 3.0 |

## Resources

| Name | Type |
|------|------|
| azurerm_resource_group.main | resource |
| azurerm_storage_account.main | resource |

## Inputs

| Name | Description | Type | Required |
|------|-------------|------|----------|
| resource_group_name | Name of the resource group to create | `string` | yes |
| storage_account_name | Name of the storage account (must be globally unique, lowercase, 3-24 chars) | `string` | yes |
| location | Azure region to deploy resources into | `string` | yes |

## Outputs

| Name | Description |
|------|-------------|
| resource_group_id | ID of the created resource group |
| storage_account_id | ID of the created storage account |

## Notes

- Storage account is created with `account_tier = "Standard"` and `account_replication_type = "LRS"`.

## License

MIT