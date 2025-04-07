---
icon: arrow-down-to-square
---

# Terraform

Terraform ist ein Open-Source Infrastructure-as-Code (IaC) Tool von HashiCorp. Es erlaubt, Cloud-Infrastruktur deklarativ zu definieren, zu versionieren und automatisiert bereitzustellen. In Kombination mit Microsoft Azure kann damit beispielsweise eine komplette Infrastruktur bestehend aus App Services, Datenbanken und Netzwerken erstellt werden.

### Nutzung mit Azure

Um Terraform mit Azure zu nutzen, wird zunächst der Azure-Provider definiert. Dieser stellt die Verbindung zwischen Terraform und der Azure-Cloud her:

```hcl
provider "azurerm" {
  features {}
}
```

Ein einfaches Beispiel für die Definition einer Ressourcengruppe in Azure sieht so aus:

```hcl
resource "azurerm_resource_group" "main" {
  name     = "rg-task-tracker"
  location = "westeurope"
}
```

Die empfohlene Projektstruktur enthält mehrere `.tf`-Dateien:

* `main.tf` für die Ressourcen-Definitionen
* `variables.tf` für Variablen
* `outputs.tf` für Ausgabevariablen
* `providers.tf` für die Provider-Konfiguration
* `backend.tf` (optional) für die Konfiguration eines Remote-State

### Wichtige Terraform-Befehle

* `terraform init` initialisiert das Projekt und lädt den Provider.
* `terraform plan` zeigt geplante Änderungen (was wird erstellt, geändert oder gelöscht).
* `terraform apply` wendet die Konfiguration an und erstellt die Ressourcen.
* `terraform destroy` löscht die definierten Ressourcen.
* `terraform fmt` formatiert alle `.tf`-Dateien nach dem Terraform-Standard.
* `terraform validate` prüft die Konfiguration auf Syntaxfehler.

### Remote State

Gerade bei Teamprojekten wird empfohlen, den Terraform State zentral zu speichern. Dies geschieht meist über Azure Storage:

```hcl
hclKopierenBearbeitenterraform {
  backend "azurerm" {
    resource_group_name  = "tfstate-rg"
    storage_account_name = "tfstateaccount"
    container_name       = "tfstate"
    key                  = "terraform.tfstate"
  }
}
```

Der Storage Account und der Container müssen vorher existieren – entweder manuell oder ebenfalls über Terraform erstellt.

### Authentifizierung

Für lokale Entwicklungsumgebungen erfolgt die Authentifizierung über das Azure CLI:

```bash
az login
```

Terraform verwendet automatisch das aktuell angemeldete Azure-Konto.

### Dokumentation

mehr findet man auf [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs) für azure

