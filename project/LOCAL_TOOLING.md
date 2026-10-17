# Zero-cost tooling and setup contract

## Recommended implementation
Python 3.11+, pandas or DuckDB for calculations, Pydantic or jsonschema for contracts, pytest for tests, Streamlit for local UI (or an equivalent review-capable CLI), standard JSON/Markdown files for storage. No vector database or RAG pipeline is necessary: the evidence packet is built directly from computed metrics.

Use Ollama locally with Qwen2.5-1.5B-Instruct as an initial candidate; the publisher model card identifies Apache-2.0. The Ollama qwen2.5:1.5b package is approximately 986 MB at the reference check; record actual digest and size at install because tags may change. Do not generalise its licence to all Qwen variants.

## Initial local model route
Install Ollama using its official distribution, then:
```text
ollama pull qwen2.5:1.5b
ollama run qwen2.5:1.5b
```
Bind the application to the local runner at http://localhost:11434. Use the structured-output API's schema facility, plus independent schema and semantic validation. Record runner version, model digest, quantisation, prompt hash, temperature, context/output limits and supported seed configuration.

## Hardware and feasibility
Plan to use an existing CPU laptop with around 8 GB system RAM as an initial trial, short evidence packets and bounded outputs. This is a planning assumption, not a measured minimum or performance guarantee. Model weights, context and other applications require additional memory. Benchmark on the team's actual machine in the first stage; record RAM, CPU/GPU, disk use and cold/warm timing. Do not require buying hardware.

If resources are tight, reduce context/output, quantise with a documented compatible local runner or share an existing team computer for inference. Templates and cached runs support development but final acceptance still includes a fresh local model run. Do not substitute a paid endpoint or a trial quota.

## Team reproduction contract
The delivered README must contain tested Windows and/or documented supported-OS commands for: creating an environment, installing locked dependencies, acquiring/verifying sources, running validation, building KPIs/evidence, generating a baseline, generating with the local model, launching review UI, testing, evaluating and exporting. These commands must invoke real delivered entry points; this specification does not pretend those application commands already exist.

Commit a dependency lock or exact tested versions and .env.example with local defaults only. No secrets, model weights or virtual environments in Git. After initial downloads the full core flow must run without internet.

## Cost declaration
Required licence/API/hosting spend: £0 on existing hardware. Existing electricity/internet and download/storage use still exist; no promise of free hardware. Cloud deployment, paid APIs and free trials are optional and excluded from the acceptance path. Submit a cost table confirming actual core spend and dependencies.
