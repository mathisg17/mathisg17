<div align="center">

# Mathis

**Founder & engineer at [Aeon HQ](https://github.com/Aeon-HQ)**

I build the software French SMBs run on, and the systems underneath it.

[![Aeon Systems](https://img.shields.io/badge/Aeon_Systems-aeon--systems.fr-0b0b0c?style=flat-square)](https://aeon-systems.fr)
[![StrucTime](https://img.shields.io/badge/StrucTime-structime.app-2563eb?style=flat-square)](https://structime.app)

</div>

---

### Languages

![C#](https://img.shields.io/badge/C%23-512BD4?style=for-the-badge&logo=csharp&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![Rust](https://img.shields.io/badge/Rust-000000?style=for-the-badge&logo=rust&logoColor=white)
![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=for-the-badge&logo=c&logoColor=black)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![Assembly](https://img.shields.io/badge/Assembly-6E4C13?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)

**C# / .NET** carries the StrucTime backend: vertical slices, EF Core, a message bus, and the
accounting rules that have to be right. **TypeScript and React** make the product surface, typed
end to end against the OpenAPI contract. **Rust** runs the shared platform behind it (auth,
billing, files, notifications, print). **C, C++ and assembly** are for the low-level work: kernel
and boot code, context switching, hand-written SIMD kernels, on RISC-V 64, AArch64 and x86-64.
**Go and Python** handle tooling, data, and model training.

### StrucTime

Field-oriented SaaS for French SMBs, in production. Quotes, invoices, time tracking, payroll and
site management across 33 modules, with French compliance built in rather than bolted on:
e-invoicing and the 2026 reform, NF525 sealing, GDPR, payroll rules, and the paperwork the
construction sector runs on.

### Training models

I train models, I don't just call them. Fine-tuning with PyTorch and the Hugging Face stack
(PEFT, LoRA and QLoRA, quantised training), and serving what comes out of it.

The research side is **StrucTime LWM**, a world model rather than a language model. It learns the
dynamics of real systems from real data, then executes them: forecasting over several horizons,
answering by simulation on the current state, and causal analysis. Because the answer is carried
by the learned dynamics instead of retrieved text, it resists hallucination by construction.
Measured held out against the seasonal baseline, on public data and identical windows, 9 of 10
domain × horizon configurations beat the reference, by up to 29% where the structure allows it.

### How I build

Multi-tenancy is enforced by PostgreSQL row-level security, forced, with the tenant set per
transaction: cross-tenant access isn't guarded against, it's impossible. Money is decimal all the
way down, cents as integers, French formatting only at the edge. Anything two people can edit at
once carries an ETag, and a conflict goes back to the user instead of overwriting a colleague.

The rest is guards rather than intentions: architecture tests, a deployment gate, and a synthetic
route × role probe after every release. A comment that lies costs more than no comment at all.
