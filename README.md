# trafficsign

Intelligente Steuerung von Verkehrsinfotafeln

TrafficSign ist eine von ADDIX entwickelte Lösung zur dynamischen Steuerung von Verkehrsinfotafeln. Mithilfe von NGSI-LD-konfigurierten Entitäten analysiert das System relevante Informationen und trifft darauf basierend automatisierte Entscheidungen zur Anzeige von Verkehrsinformationen.

### Einsatz im Projekt

#### 🚦 Intelligente Entscheidungsfindung mit NGSI-LD

Durch die Verwendung von NGSI-LD-Config-Entitäten kann TrafficSign Daten aus verschiedenen Quellen verarbeiten und darauf basierend die optimale Anzeige für Verkehrsteilnehmer bestimmen. Dies ermöglicht eine situationsabhängige Steuerung, die sich flexibel an aktuelle Gegebenheiten anpasst.

#### 📢 Dynamische Anzeige von Verkehrsprogrammen

Sobald eine Entscheidung getroffen wurde, fordert TrafficSign die passenden Anzeigemodi für die Verkehrsinfotafeln an. Ob Stauwarnungen, Umleitungshinweise oder Umweltinformationen – die Inhalte werden in Echtzeit angepasst, um die Verkehrssituation bestmöglich zu unterstützen.

Mit TrafficSign wird die digitale Verkehrssteuerung intelligenter, effizienter und flexibler, indem Echtzeitdaten und semantische Kontexte für eine automatisierte Informationsbereitstellung genutzt werden.


## Voraussetzungen

* Kubernetes 1.23+
* Helm 3.8.0+

## Installation

```bash
$ cd trafficsign
$ helm install <my-release> helm --values <values file> -n <namespace>
```

alternativ:

```bash
$ helm upgrade --install <my-release> helm --values <values file> -n <namespace>
```

Beispiel:

```bash
$ helm upgrade --install my-release helm -n my-namespace --create-namespace --values <values file>
```

## Parameter
Die wichtigen Parameter werden im values.yaml konfiguriert.

| Name                    | Description                                     | Value  |
|:------------------------|:------------------------------------------------|:-------|
| env.port                | Service port                                    | 8088   |
| env.debugLevel          | Debug level                                     | info   |
| env.orionUrl            | Address of an ngsi-ld context broker            | http://localhost |
| env.tenant              | Tenant to use                                   | anonymous |
| env.quantumleapUrl      |                                                 | http://quantumleap.quantumleap.local:8000/v2/notify |

## Upgrading the chart

```bash
$ helm upgrade <my-release> helm --values <values file> -n <namespace>
```

## License

Copyright © 2024 ADDIX GmbH.
