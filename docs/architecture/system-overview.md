# System Overview

This project implements a self-hosted AI development environment designed to support and improve software development workflows using local LLMs, securely and distributed across multiple machines.

The system is split across two machines: a dedicated server for hosting low level AI services and interfaces and a main development workstation used for software development hosting high performance AI services. Together, these systems form a fully private, local AI development platform without reliance on external APIs.

## Document Structure

This document provides a high-level overview of the system architecture and design decisions.

For detailed implementation, see:
- `docs/architecture/` - System design, network architecture, and AI workflows
- `docs/security/` - SSH authentication, firewall configuration, and Tailscale integration
- `docs/setup-guides/` - Install and configuration guides

## Design Goals

The system was designed around the following objectives:
- Local, private AI development without external API dependency
- Secure remote local access across multiple devices
- Distributed load across available hardware
- No recurring operation costs
- AI-assisted software engineering workflows
- Modular and scalable infrastructure

## High-level Architecture

The environment is split across two machines:
|Machine|	Primary Role|
|--------|------------|
|Server|	Always-on AI services and infrastructure hosting|
|Development Workstation|	Software development and high-performance model inference|

Both machines are connected via a private Tailscale network, enabling secure encrypted communication without public port exposure.

## Server

The server acts as the infrastructure node of the system.

The server hosts:
|Software | Role |
|---------|-------|
|Debian 12| Lightweight OS|
|CasaOS | system and container management|
|Ollama |LLM hosting|
|Open WebUI| browser-based AI interface|

The server is built on repurposed low-specification hardware configured for reliable 24/7 operation. It is primarily used for hosting services and lightweight AI workloads. This can be reconfigured for heavier workloads with more appropriate hardware.

For setup details, see:
- [docs/setup-guides/casaos-install.md](../docs/setup-guides/casaos-install.md)
- [docs/setup-guides/ollama-install.md](../docs/setup-guides/ollama-install.md)
- [docs/setup-guides/debian-install.md](../docs/setup-guides/debian-install.md)
- [docs/setup-guides/open-webui-install.md](../docs/setup-guides/open-webui-install.md)

## Development workstation

The development workstation is the primary engineering environment and compute node.

It is used for:
- VS Code development
- Roo Code AI integration
- High-performance local AI model hosting
- System design and software implementation

The stronger the hardware on this machine enables the use of larger models for planning, coding, and code review tasks.

## Security

Security is implemented using a layered model:
- SSH key authentication for secure remote administration
- UFW firewall rules to restrict system access
- Tailscale private networking for encrypted device communication

This ensures that no services are exposed publicly while maintaining secure remote access across devices.

For more details on configuration, see:
`docs/security/`

## AI Infrastructure

Ollama is used as the core model hosting platform across both machines. It provides a consistent API for running local language models and integrates well with both Open WebUI and Roo Code.

### Model Distribution

|Model	|Host Machine|	Primary Role|
|-----|-----|------|
|Llama 3.2|	Server|	Lightweight assistant for documentation, summaries, and research|
|Qwen 2.5 Coder (7B)|	Server|	Lightweight coding tasks and remote assistance|
|Qwen 2.5 Coder (14B)|	Development Workstation|	Primary code generation and implementation model|
|Qwen 3 (14B)|	Development Workstation|	System design, reasoning, and architecture planning|
|DeepSeek R1 (14B)|	Development Workstation|	Code review, debugging, and analysis|

For additional details, see:
[docs/architecture/ai-workflow.md](../docs/architecture/aiworkflow.md)

## Roo Code Integration

Roo Code is integrated into the VS Code environment to enable direct integration with local and remote models via the Ollama API.

Using the Tailscale network, different models can be assigned to specialised development roles, enabling structured AI-assisted workflows for:
- Planning
- Implementation
- Debugging
- Code review

## Summary

This system combines Linux server administration, secure networking, local AI infrastructure, and AI-assisted software engineering workflows into a unified self-hosted development environment.

It provides a foundation for scalable software development while demonstrating practical experience in:
- Systems architecture
- Networking and security
- Local AI development
- Development workflow automation


