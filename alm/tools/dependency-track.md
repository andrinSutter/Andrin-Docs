---
icon: chart-radar
---

# Dependency Track

**Dependency-Track** ist ein Tool, das dir hilft, den Überblick über die **Bibliotheken und Abhängigkeiten** in deinem Projekt zu behalten – besonders in Bezug auf **Sicherheitslücken**.

### 🛠 Was macht es?

* Scannt deine verwendeten Libraries (z. B. NPM, NuGet, Maven, etc.)
* Prüft, ob bekannte **Sicherheitslücken (CVEs)** in deinen Abhängigkeiten enthalten sind
* Zeigt dir, welche Schwachstellen kritisch sind und wo du Updates brauchst
* Unterstützt SBOMs (Software Bill of Materials), z. B. im **CycloneDX-Format**

### Hauptfunktionen

* **Hochwertige Metriken und Trends**: Bietet umfassende Metriken und Trends zu den übernommenen Risiken für alle Projekte und Komponenten im Portfolio.
* **Schnelle Reaktion auf erkannte Schwachstellen**: Ermöglicht eine rasche Reaktion auf erkannte Schwachstellen bei Projekten, die von gefährdeten Komponenten betroffen sind.
* **Identifizierung veralteter Komponenten**: Erkennt Komponenten, die nicht auf dem neuesten Stand sind und somit indirekt die Gesundheit und das Risiko von Projekten beeinflussen.

### Zugriff

Über [https://dependency-track.alm.buhlergroup.com/login?redirect=%2Fdashboard](https://dependency-track.alm.buhlergroup.com/login?redirect=%2Fdashboard) kommt man zum Login von Buhlergroup.&#x20;

Die Berechtigungen kann man beim ServiceDesk mit diesem Mail template anfrage:

```
Subject: Secure Development > Setup Dependency Track
Dear ALM Team

I would like to use the Dependency Track for my project:
- Name of the project in Azure DevOps:
- Name and ID of the parent work item where findings should be added to:
- Name of the team in Dependency Track (recommendation: same as Azure DevOps project name):
- Are you already using pipelines: yes/no

Best Regards,
```

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

