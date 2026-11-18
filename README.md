# Azure Network Simulator (AzNetSim) — Documentation & Scripts

This public repository hosts **user documentation, an Azure collector script, and sample JSON topologies** for **[Azure Network Simulator (AzNetSim)](https://aznet-simulator.com)**.

> **Feedback has moved:** Please report bugs and request features in the [main application's issue tracker](https://github.com/erjosito/vwan-visual-topology/issues). The application now covers VNets, hub-and-spoke, Virtual WAN and hybrid networks. This repository stays available for existing documentation, script and sample links.

## Documentation & Worked Examples

- **Web Documentation (with 1-click "Open in Simulator" links):** [English (`https://vwan-simulator.com/docs/`)](https://vwan-simulator.com/docs/) | [日本語 (`https://vwan-simulator.com/docs/?lang=ja`)](https://vwan-simulator.com/docs/?lang=ja)
- **Markdown User Guide & Annotated Screenshots:** [English (`docs/README.md`)](./docs/README.md) | [日本語 (`docs/README.ja.md`)](./docs/README.ja.md)
- **Azure Collector Script (`collect-azure-vwan.ps1`):** [scripts/collect-azure-vwan.ps1](./scripts/collect-azure-vwan.ps1)
- **Downloadable Sample Topologies (.json):** [English (`samples/README.md`)](./samples/README.md) | [日本語 (`samples/README.ja.md`)](./samples/README.ja.md)

| Sample Topology | Key Features Demonstrated | Try Live | JSON File |
|---|---|---|---|
| **1. Hub Routing Preferences** | ExpressRoute vs VPN vs ASPath hub routing preference | [Open in Simulator](https://vwan-simulator.com/?sample=hub-routing-preferences) | [hub-routing-preferences.json](./samples/hub-routing-preferences.json) |
| **2. Secured vHub & Routing Intent** | Azure Firewall, PrivateTraffic & InternetTraffic Routing Intent | [Open in Simulator](https://vwan-simulator.com/?sample=secured-hub-routing-intent) | [secured-hub-routing-intent.json](./samples/secured-hub-routing-intent.json) |
| **3. Spoke BGP Peering & NVA Transit** | Spoke NVA (65100) BGP peering with vHub RS (65515) | [Open in Simulator](https://vwan-simulator.com/?sample=spoke-bgp-nva-transit) | [spoke-bgp-nva-transit.json](./samples/spoke-bgp-nva-transit.json) |
| **4. 3-Hub All-Features & Asymmetric Routing** | 3 hubs, ER/VPN/SD-WAN, custom route tables, NVA spoke, forward vs return path asymmetry | [Open in Simulator](https://vwan-simulator.com/?sample=three-hub-all-features-asymmetric) | [three-hub-all-features-asymmetric.json](./samples/three-hub-all-features-asymmetric.json) |

## Azure Collector Script

To capture a read-only snapshot of an existing Azure Virtual WAN environment (structure and optional effective routes) for import or comparison in the simulator:

```powershell
Invoke-WebRequest -Uri 'https://raw.githubusercontent.com/erjosito/vwan-visual-topology-feedback/main/scripts/collect-azure-vwan.ps1' -OutFile ./collect-azure-vwan.ps1
pwsh ./collect-azure-vwan.ps1 -VirtualWanId '/subscriptions/<subscription-id>/resourceGroups/<resource-group>/providers/Microsoft.Network/virtualWans/<wan-name>' -OutputFile ./azure-vwan-observation.json -IncludeEffectiveRoutes
```

## Submitting Feedback

Please [open new reports in the main application's issue tracker](https://github.com/erjosito/vwan-visual-topology/issues/new). The simulator's **Feedback** form is being updated to use that same tracker; already published app versions may still link here until the next explicit release. Existing reports are being reviewed and either resolved with evidence or transferred with their original authorship and discussion preserved.

> **Privacy & Security Notice:** Please do not include secrets, credentials, or confidential customer network topologies/IP addresses in public issues. Use sanitized or synthetic prefixes when sharing reproduction steps.
