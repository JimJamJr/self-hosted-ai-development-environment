# self-hosted-ai-development-environment

This project documents the design and implementation of a customisable self-hosted AI development environment built to support the development of my software engineering projects. The aim was to create a secure, customisable system that can run large language models locally across multiple different machines, removing the need for paid APIs while also allowing me to create bespoke development workflows. 

The environment combines Linux administration, networking, containerisation, and AI infrastructure to provide a central platform to access language models to help develop, test, and document software projects.

## Technology

This system is built using the following softwares:
- Debian 12 Linux
- Docker
- CasaOS
- Ollama (various models detailed in `ai-workflows.md`)
- Open WebUI
- Roo Code
- Tailscale

## Objectives

- Eliminate API usage costs by running models locally
- Create a secure environment for AI-assisted software development
- Build custom workflows for different development tasks
- Gain experience designing and managing self-hosted AI infrastructure
- Experiment with improving software development workflows using AI

## Skills 

- Linux administration
- Networking
- Containerisation
- AI infrastructure
- Workflow design
- Documentation

## Documentation

The repository is organised into individual sections covering the technologies and design decisions used throughout the project. This includes:

- Networking `network-architecture.md`
- Security `security/..`
- AI workflows `ai-workflows.md`
- System architecture `system-overview.md`
- Setup guides `setup-guides/..`
