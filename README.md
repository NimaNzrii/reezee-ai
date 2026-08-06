<div align="center">
  <img src="assets/reezee-mark.svg" alt="ReeZee AI logo" width="124" />

# ReeZee AI for Photoshop

### Native Photoshop control. Your ComfyUI stack. Any MCP-capable agent.

**ReeZee turns natural-language intent into real, editable Photoshop documents — while keeping your models, workflows, layers, masks, typography, and effects under your control.**

[![Project Status](https://img.shields.io/badge/status-private%20preview-B2E54E?style=for-the-badge&labelColor=1C211D)](#availability)
[![Adobe Photoshop](https://img.shields.io/badge/Adobe-Photoshop-31A8FF?style=for-the-badge&logo=adobephotoshop&logoColor=white)](#what-reezee-controls)
[![ComfyUI](https://img.shields.io/badge/ComfyUI-bring%20your%20own%20models-B2E54E?style=for-the-badge&labelColor=1C211D)](#your-models-your-workflows)
[![MCP](https://img.shields.io/badge/MCP-agent%20ready-A78BFA?style=for-the-badge&labelColor=1C211D)](#use-the-agent-where-you-work)

[Why ReeZee](#why-reezee) · [Capabilities](#what-reezee-controls) · [How it works](#how-it-works) · [Legacy](#from-blue-pixel-to-reezee) · [Availability](#availability)

</div>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="assets/brand-banner.svg">
  <source media="(prefers-color-scheme: light)" srcset="assets/brand-banner.svg">
  <img alt="ReeZee AI connects AI chat, Adobe Photoshop, ComfyUI, and MCP clients" src="assets/brand-banner.svg" width="100%">
</picture>

> [!IMPORTANT]
> **ReeZee is a from-scratch successor to the original [ComfyUI Photoshop Plugin](https://github.com/NimaNzrii/comfyui-photoshop).** It preserves the core Photoshop ↔ ComfyUI workflow and expands it into a deeper system for native document construction, agent-driven editing, deterministic layout, and external MCP control.

---

## Why ReeZee

Most AI image tools stop at a generated bitmap. ReeZee is built for the work that comes next.

<table>
<tr>
<td width="33%" valign="top">

### ◈ Build, don't paste

Create **real Photoshop structure**: editable layers, live text, masks, selections, adjustments, transforms, and effect stacks.

</td>
<td width="33%" valign="top">

### ◇ Keep your AI stack

Connect Photoshop to **ComfyUI** and continue using your own checkpoints, LoRAs, ControlNets, nodes, and existing workflows.

</td>
<td width="33%" valign="top">

### ⟡ Work with agents

Use ReeZee's in-plugin chat or connect an external MCP-capable client to inspect and operate on Photoshop through a shared tool surface.

</td>
</tr>
</table>

> [!NOTE]
> ReeZee is deliberately focused on the combination of **deep UXP-native Photoshop control + deterministic layout and effects + ComfyUI + MCP**. It is not a replacement for Photoshop, and it does not depend on Adobe Firefly for its ComfyUI workflow.

---

## See ReeZee in action

<a href="assets/plugin-preview.svg">
  <img src="assets/plugin-preview.svg" alt="Placeholder preview of the ReeZee AI Photoshop interface" width="100%" />
</a>

> [!TIP]
> **Screenshot placeholder:** replace `assets/plugin-preview.svg` with a final product screenshot or demo cover when the install-tested release is ready. Keep the same path to update this README automatically.

---

## What ReeZee controls

<details open>
<summary><strong>Photoshop-native creation</strong></summary>
<br>

| Surface | What ReeZee can work with |
|:--|:--|
| **Documents & layers** | Create, inspect, rename, group, reorder, duplicate, transform, and manage layer structures |
| **Typography** | Create editable text with precise placement informed by real font bounds |
| **Effects & appearance** | Build effect stacks, adjustments, fills, opacity treatments, and reusable styling recipes |
| **Masks & selections** | Create and manipulate masks and selections, including AI-assisted subject masking |
| **Smart workflows** | Work with Smart Objects, content-aware fill, image statistics, and document layout analysis |
| **Safety & continuity** | Keep history-aware snapshots and surface approval before selected destructive actions |

</details>

<details>
<summary><strong>Deterministic layout & effects engine</strong></summary>
<br>

ReeZee includes a purpose-built rendering engine for constructing layered Photoshop compositions from structured design intent.

- **Editable output** instead of a flattened final image
- **Anchor-aware text placement** based on measured font bounds
- **Repeatable layout construction** for frames, text, groups, and visual effects
- **Ordered effect compilation** for complex, stacked appearances
- **Document-aware updates** after agent operations

This engine is the heart of ReeZee: AI proposes the composition, but Photoshop remains the final, editable source of truth.

</details>

<details>
<summary><strong>Vision & document awareness</strong></summary>
<br>

The agent can reason with more than a chat transcript. ReeZee provides document and image context through capabilities such as:

- Layer-tree and layout summaries
- Vision analysis
- Image statistics
- Layout digest generation
- AI subject masking with BiRefNet
- Authored design guidance for more informed visual decisions

</details>

<details>
<summary><strong>Reusable knowledge</strong></summary>
<br>

ReeZee is being built to retain useful creative knowledge without hiding what it is doing.

- Save repeatable multi-step agent recipes
- Reuse learned workflows with validation and history checkpoints
- Extract selected layer effects from PSD files into versioned local Style Packs
- Import and export Style Packs as portable JSON assets
- Keep bundled presets separate from user-authored style libraries

</details>

---

## Your models. Your workflows.

ReeZee keeps the original plugin's core promise: bring ComfyUI into the Photoshop workflow instead of forcing creators into a separate, closed generation stack.

```mermaid
flowchart LR
    PS["Photoshop selection / layers"] --> RZ["ReeZee bridge"]
    RZ --> CU["Your loaded ComfyUI workflow"]
    CU --> M["Your checkpoints · LoRAs · ControlNets"]
    M --> CU
    CU --> G["Generated results"]
    G --> RZ
    RZ --> PS2["Photoshop document"]
```

### What carries forward from the original plugin

- Photoshop-to-ComfyUI image handoff
- Selection and layer context
- Mask-aware creative workflows
- Local or remote ComfyUI connection paths
- Results returning to the Photoshop-side experience
- Freedom to choose the models behind your workflow

> [!WARNING]
> ReeZee can queue the workflow currently loaded in ComfyUI. It does **not** yet author a complete ComfyUI graph from a chat prompt. We would rather state that boundary clearly than market a feature that is not ready.

---

## Use the agent where you work

<table>
<tr>
<td width="50%" valign="top">

### Inside Photoshop

Talk to ReeZee from the plugin panel. The agent can inspect document context, plan operations, request approval where needed, and execute through Photoshop's UXP APIs.

</td>
<td width="50%" valign="top">

### From an external AI client

Connect an MCP-capable client such as Claude Desktop or Cursor and expose the same Photoshop-oriented capabilities through ReeZee's local bridge.

</td>
</tr>
</table>

> [!NOTE]
> External MCP support is implemented, but the public preview remains gated while end-to-end reliability and installation are hardened.

---

## How it works

<img src="assets/workflow.svg" alt="ReeZee workflow from user request through native Photoshop and ComfyUI operations" width="100%" />

1. **Describe the outcome** in ReeZee's chat or through an MCP-capable client.
2. **ReeZee reads relevant context** from the active Photoshop document.
3. **The agent chooses bounded tools** for layout, layers, text, effects, masks, selections, or pipeline actions.
4. **Photoshop executes native operations** through UXP, DOM APIs, batch operations, and native image/layout helpers.
5. **ComfyUI joins when needed**, running the workflow you already control.
6. **The document stays editable** so the creator — not the model — has the final say.

---

## From Blue Pixel to ReeZee

The original **ComfyUI Photoshop Plugin** proved that creators wanted ComfyUI inside Photoshop. It grew to include real-time workflow sync, selection cropping and padding, mask previews, port configuration, remote ComfyUI connectivity, shortcuts, multilingual workflow support, and in-plugin updating.

ReeZee takes that foundation much further.

| | Original plugin | ReeZee AI |
|:--|:--:|:--:|
| Photoshop ↔ ComfyUI bridge | ✓ | ✓ |
| Selection, crop, mask, and layer handoff | ✓ | ✓ |
| Use your own ComfyUI models | ✓ | ✓ |
| In-Photoshop AI chat | — | ✓ |
| Native layer and document operations | Limited | **Deep UXP-native surface** |
| Editable AI-built layouts | — | ✓ |
| Precise typography and effect construction | — | ✓ |
| Document vision and layout awareness | — | ✓ |
| External MCP agent control | — | ✓ |
| Reusable agent recipes and Style Packs | — | **In preview** |

<details>
<summary><strong>Explore the original project</strong></summary>
<br>

The legacy repository remains available at **[NimaNzrii/comfyui-photoshop](https://github.com/NimaNzrii/comfyui-photoshop)**, with more than 1,000 GitHub stars and a community that helped shape the direction of ReeZee.

If the original plugin helped your workflow, thank you. ReeZee is being built as the next chapter — not a cosmetic version bump.

</details>

---

## Availability

> [!CAUTION]
> **ReeZee is not yet published as a public, install-ready release.** The current project is a private preview while packaging, fresh-install verification, host-level testing, security cleanup, and reliability work are completed.

### Current preview status

- [x] Deep Photoshop operation layer implemented
- [x] Deterministic layout and effects engine implemented
- [x] ComfyUI bridge implemented
- [x] In-plugin agent experience implemented
- [x] MCP tool surface implemented
- [x] Focused tests for agent memory and Style Pack subsystems
- [ ] Clean ReeZee `.ccx` verified on a fresh Photoshop installation
- [ ] Full Photoshop-host demo matrix completed
- [ ] Public download and installation guide published

**Want to evaluate ReeZee, discuss licensing, or follow the release?**

<div align="center">

[![Email](https://img.shields.io/badge/Email-nimanzriart%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:nimanzriart@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-NimaNzrii-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/NimaNzrii)
[![Discord](https://img.shields.io/badge/Discord-Join%20the%20community-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/invite/3eHAMWnx7Y)

</div>

---

## Frequently asked questions

<details>
<summary><strong>Does ReeZee replace ComfyUI?</strong></summary>
<br>
No. ReeZee connects Photoshop to ComfyUI and coordinates the creative workflow. Your ComfyUI installation, workflows, models, and nodes remain yours.
</details>

<details>
<summary><strong>Does ReeZee flatten every result?</strong></summary>
<br>
No. A central goal is to construct editable Photoshop documents with real layers, text, masks, adjustments, and effects wherever the operation supports it. Generated imagery can still enter the document as pixels, but the surrounding composition does not need to become one flattened image.
</details>

<details>
<summary><strong>Does it use Adobe Firefly?</strong></summary>
<br>
ReeZee's ComfyUI bridge is independent of Adobe's generative stack. Optional providers may be available for other generation paths, but your local ComfyUI workflow does not require Firefly.
</details>

<details>
<summary><strong>Can ReeZee build a ComfyUI workflow from scratch?</strong></summary>
<br>
Not yet. The current integration can send Photoshop context to ComfyUI and queue the workflow already loaded there. Full graph authoring is not advertised as a working capability.
</details>

<details>
<summary><strong>Is this repository the plugin source code?</strong></summary>
<br>
No. This repository is the public presentation home for ReeZee. The implementation remains private during the preview and evaluation phase.
</details>

<details>
<summary><strong>Can I use ReeZee commercially?</strong></summary>
<br>
Commercial terms and preview access are handled directly. Contact **[nimanzriart@gmail.com](mailto:nimanzriart@gmail.com)** to discuss licensing or evaluation.
</details>

---

## Project principles

- **Native before simulated** — use modern Photoshop UXP capabilities rather than fragile legacy scripting.
- **Editable before flattened** — preserve document structure whenever possible.
- **Local freedom before lock-in** — keep ComfyUI models and workflows in the creator's hands.
- **Honest boundaries before hype** — distinguish implemented, verified, preview, and planned capabilities.
- **Creator control before autonomy theater** — the agent helps build; the human owns the final document.

<div align="center">

<img src="assets/reezee-mark.svg" alt="ReeZee AI" width="76" />

### Photoshop is the canvas. ReeZee connects the intelligence around it.

<sub>Created by <a href="https://github.com/NimaNzrii">Nima Nazari</a> · Successor to the original <a href="https://github.com/NimaNzrii/comfyui-photoshop">ComfyUI Photoshop Plugin</a></sub>

<br><br>

[![Follow](https://img.shields.io/github/followers/NimaNzrii?style=social)](https://github.com/NimaNzrii)
[![Legacy Stars](https://img.shields.io/github/stars/NimaNzrii/comfyui-photoshop?style=social&label=Legacy%20project)](https://github.com/NimaNzrii/comfyui-photoshop)

</div>
