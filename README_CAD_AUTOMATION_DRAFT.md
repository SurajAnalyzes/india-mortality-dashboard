# AI-Powered CAD Automation with Antigravity, FreeCAD, and MCP

A work-in-progress exploration of connecting an AI coding agent to FreeCAD so it can assist with CAD operations for a real rubber component.

## Project overview

The project explores an AI-assisted workflow for engineering drawing interpretation, 3D part modeling, and early-stage mold-design planning.

The current demonstration uses a 3D model of an NBR rubber spark-plug seal identified in the source drawing as AAN68057 / AF101614 MOD-02. The screenshot available during documentation shows the component open in FreeCAD 1.1.3, along with logs from the FreeCAD AI/MCP service.

> **Status: Prototype / workflow exploration.** This repository documents the workflow and design direction. It does not represent a validated manufacturing tool or a production-ready mold.

## Goals

- Explore how an AI agent can interact with CAD software through tools rather than only generating text or code.
- Connect Antigravity CLI to FreeCAD using a Python-based Model Context Protocol (MCP) server.
- Inspect and model an NBR rubber seal in FreeCAD.
- Plan a four-cavity compression-mold concept for small-batch trials.
- Identify the engineering inputs required before tooling can be released for manufacturing.

## Tools and technologies

- **Antigravity CLI** — AI-agent interface used during the workflow.
- **FreeCAD 1.1.3** — 3D CAD modeling and geometry inspection.
- **Python** — bridge/server scripting and CAD automation.
- **Model Context Protocol (MCP)** — exposes selected FreeCAD tools to the AI agent.

## Workflow explored

1. **Review the engineering drawing.** Identify the target part and read the dimensions and material notes. Dimensions must be checked against the authoritative drawing before they are used for tooling.
2. **Set up FreeCAD.** Install FreeCAD and prepare a Python environment for the MCP server.
3. **Connect the AI agent.** Configure the MCP client to launch the FreeCAD MCP server. Keep local configuration files and any credentials out of version control.
4. **Test tool access.** Check the connection and use the available tools for CAD operations, view control, and geometry inspection.
5. **Model the component.** Create and inspect the 3D rubber-seal model in FreeCAD.
6. **Plan the next stage.** Explore a four-cavity compression-mold layout for small-batch trials. The mold design remains a concept until dimensions, tooling strategy, and manufacturing constraints are reviewed.

## Part and mold context

The target is an NBR rubber seal, Shore 60A, from drawing identifiers AAN68057 / AF101614 MOD-02. The intended follow-on is a four-cavity compression mold.

A compression mold concept must be designed around the actual press and validated compound/process data. Before manufacturing, the following remain to be confirmed:

- Authoritative drawing dimensions, tolerances, and any unspecified features such as the shoulder/U-cut.
- Rubber compound grade, cure characteristics, shrinkage data, charge mass, and flash allowance.
- Parting line, draft, venting, release, ejection, and cavity/core arrangement.
- Press platen size, daylight, closing force, temperature, and trial requirements.
- Tool material, heat treatment, surface finish, and inspection plan.

**Do not use this prototype as manufacturing tooling without engineering review and validation.** Estimated shrinkage, tolerances, and un-dimensioned features must not be guessed.

## Repository status

This repository starts with documentation only. CAD files and automation scripts should be added when their authorship, sharing rights, and execution status are clear. The draft mold macro discussed during development was reported not to open in FreeCAD and is therefore **not described here as working or validated**.

Suggested future structure:

```text
.
├── README.md
├── docs/
│   ├── architecture.md
│   └── engineering-validation.md
├── screenshots/
│   └── freecad-seal-model.png
└── cad/
    └── (validated FreeCAD files only)
```

## Privacy and sharing

Do not commit API keys, access tokens, local machine paths, private MCP configuration, or confidential/proprietary engineering drawings. Before publishing product drawings or screenshots, confirm that you have permission to share them.

## Author

Suraj Kadam

---

*This is an educational engineering and automation prototype. All dimensions, tooling assumptions, and manufacturing decisions require confirmation against the approved drawing and process data.*
