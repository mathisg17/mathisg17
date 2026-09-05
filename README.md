<div align="center">

# Mathis

**Founder & engineer at [Aeon HQ](https://github.com/Aeon-HQ)**

I build the software French SMBs actually run on — and, underneath it, the systems it runs on.

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

- **C# / .NET** — the StrucTime backend: vertical slices, EF Core, a message bus, and the
  accounting rules that must not be wrong.
- **TypeScript / React** — the product surface, typed end to end against the OpenAPI contract.
- **Rust** — the shared platform behind the product: auth, billing, files, notifications, print.
- **C, C++, Assembly** — the low-level side: kernel and boot code, context switching,
  hand-written SIMD kernels, on RISC-V 64, AArch64 and x86-64.
- **Go, Python** — tooling, data work, and the AI layer.

### What I'm building

**[StrucTime](https://structime.app)** — field-oriented SaaS for French SMBs, in production.
Quotes, invoices, time tracking, payroll and site management across 33 modules, with French
compliance built in rather than bolted on: e-invoicing and the 2026 reform, NF525 sealing, GDPR,
payroll rules, and the construction sector's own paperwork.

Underneath, a shared platform of Rust services, and the systems work that goes with owning your
own stack rather than renting it.

### How I build

- **Multi-tenant by construction.** PostgreSQL row-level security, forced, tenant set per
  transaction. Cross-tenant access isn't guarded against — it's impossible.
- **Money is never a float.** Decimal all the way down, cents as integers, French formatting at
  the edge only.
- **Optimistic concurrency where it matters.** ETags and `If-Match` on every record two people
  can edit at once; a conflict returns to the user instead of overwriting a colleague.
- **Guards over intentions.** Architecture tests, a deployment gate, and a synthetic route × role
  probe after every release — because a comment that lies costs more than no comment at all.
