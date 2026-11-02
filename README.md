# Azure Virtual WAN Visual Topology Simulator — Documentation, Scripts & Public Feedback

This public repository hosts the **user documentation, Azure collector script, sample JSON topologies, and public issue tracker** for the **[Azure Virtual WAN Visual Topology Simulator](https://vwan-simulator.com)**.

## Documentation & Worked Examples

- **Web Documentation (with 1-click "Open in Simulator" links):** [https://vwan-simulator.com/docs/](https://vwan-simulator.com/docs/)
- **Markdown User Guide & Annotated Screenshots:** [docs/README.md](./docs/README.md)
- **Azure Collector Script (`collect-azure-vwan.ps1`):** [scripts/collect-azure-vwan.ps1](./scripts/collect-azure-vwan.ps1)
- **Downloadable Sample Topologies (.json):** [samples/](./samples/)

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
pwsh ./collect-azure-vwan.ps1 -SubscriptionId <subscription-id> -OutputPath ./azure-vwan-observation.json -Anonymize -IncludeEffectiveRoutes
```

## Submitting Feedback

You can submit feedback directly from the simulator (**Feedback** button in the top bar, which pre-fills the app revision and structured fields without requiring any OAuth app consent), or by [opening a new issue here](https://github.com/erjosito/vwan-visual-topology-feedback/issues/new).

> **Privacy & Security Notice:** Please do not include secrets, credentials, or confidential customer network topologies/IP addresses in public issues. Use sanitized or synthetic prefixes when sharing reproduction steps.
