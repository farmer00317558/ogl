# OpenGen Link Protocol (OGL)

<p align="center">
  <strong>The Open Standard for Deep-Linking Generative AI Prompts</strong>
</p>

<p align="center">
  <a href="https://github.com/opengen-link/ogl/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License" />
  </a>
  <a href="https://github.com/opengen-link/ogl/releases">
    <img src="https://img.shields.io/badge/version-1.0.0-green.svg" alt="Version" />
  </a>
  <a href="https://github.com/opengen-link/ogl">
    <img src="https://img.shields.io/badge/OGL-Compatible-7000FF?style=flat-square" alt="OGL Compatible" />
  </a>
</p>

---

## 📖 Introduction

**OpenGen Link (OGL)** is an open URL parameter standard designed to bridge the gap between **Prompt Libraries** (Sources) and **Generative AI Tools** (Targets).

Currently, moving a prompt from a discovery site (like Civitai or a prompt aggregator) to a generation tool (like Automatic1111 or Midjourney Web) requires tedious copy-pasting. OGL solves this by defining a standardized URL schema that allows "One-Click Generate" functionality.

### The Problem

- ❌ Copying Prompt... Switching Tab... Pasting.
- ❌ Copying Negative Prompt... Switching Tab... Pasting.
- ❌ Manually setting resolution and seeds.

### The OGL Solution

```
https://target-site.com/create?ogl_ver=1.0&prompt=cat&width=1024&height=1024
```

One link carries all the necessary metadata to recreate the generation intent.

---

## 🚀 Quick Start

### For Prompt Libraries (Source)

Construct a link using the OGL standard parameters:

```html
<a
  href="https://target-tool.com/?ogl_ver=1.0&prompt=Cyberpunk%20City&model=SDXL"
>
  Run in Target Tool
</a>
```

### For Generation Tools (Target)

Parse the URL parameters on page load and populate your UI:

```javascript
// Minimal Implementation
const params = new URLSearchParams(window.location.search);
if (params.get("ogl_ver")) {
  const prompt = params.get("prompt");
  const width = params.get("width");
  const height = params.get("height");
  // ... fill your UI inputs
}
```

---

## 📝 Specification

The current stable version is **v1.0.0**.

👉 **[Read the Full Specification (v1.0.0 English)](./spec/v1.0.0-en.md)**
👉 **[阅读完整规范 (v1.0.0 中文)](./spec/v1.0.0-zh.md)**

### Core Parameter Summary

| Parameter         | Required | Description                     |
| :---------------- | :------- | :------------------------------ |
| `ogl_ver`         | ✅       | Protocol version (e.g., `1.0`). |
| `prompt`          | ✅       | The main prompt text.           |
| `negative_prompt` | ❌       | Negative prompt text.           |
| `model`           | ❌       | Model name or hash.             |
| `seed`            | ❌       | Generation seed.                |
| `aspect_ratio`    | ❌       | e.g., `16:9`, `1:1`.            |
| `width`           | ❌       | Image width in pixels.          |
| `height`          | ❌       | Image height in pixels.         |

_(See full spec for Video, Audio, and Payload extensions)_

---

## 🛠️ Official SDK

We provide a lightweight JavaScript/TypeScript SDK to handle parsing and validation.

```bash
npm install @opengen/ogl-sdk
```

```javascript
import { OGL } from "@opengen/ogl-sdk";

// Creating a link
const link = OGL.stringify("https://site.com", {
  prompt: "A beautiful sunset over mountains",
  width: 1024,
  height: 1024,
});

// Parsing a link
const data = OGL.parse(window.location.href);
```

---

## 🤝 Adoption & Ecosystem

Add your project to the list below if you support OGL!

### Supported Libraries (Source)

- _Your prompt library here_ - Submit a PR to be listed

### Supported Tools (Target)

- _Your generation tool here_ - Submit a PR to be listed

---

## 🏆 Badge

If your website supports OGL, feel free to use this badge:

```markdown
[![OGL Compatible](https://img.shields.io/badge/OGL-Compatible-7000FF.svg)](https://github.com/opengen-link/ogl)
```

[![OGL Compatible](https://img.shields.io/badge/OGL-Compatible-7000FF.svg)](https://github.com/opengen-link/ogl)

---

## 💬 Contributing

This protocol is community-driven. We welcome RFCs (Request for Comments) and Pull Requests.

1. Open an Issue to discuss proposed changes.
2. Submit a PR to update the `spec/` directory.

### RFC Process

For major changes (new parameters, new modalities), please follow our [RFC Process](./spec/RFC-PROCESS.md).

---

## 📊 Roadmap

- [x] Core specification (v1.0.0)
- [x] Image generation parameters
- [ ] Video generation parameters
- [ ] Audio generation parameters
- [ ] Official JavaScript SDK
- [ ] Official Python SDK
- [ ] ComfyUI integration
- [ ] Automatic1111 WebUI extension

---

## 📄 License

Distributed under the MIT License. See [LICENSE](./LICENSE) for more information.

---

## 🌟 Star History

If you find this project useful, please consider giving it a star!

---

<p align="center">
  Made with ❤️ by the AI
</p>
