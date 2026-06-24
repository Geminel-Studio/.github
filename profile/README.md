<div align="center">

# Geminel Studio

### Your style, everywhere.

**The AI studio that turns your style into on-brand video, posts, and replies at scale — while you stay in control.**

</div>

---

## What we do

Geminel Studio is an **AI Social Media Management platform** for creators and brands who need to show
up everywhere, all the time — without a production team. You bring your material and your style; the
platform produces on-brand content at scale, publishes it across every major platform, and handles
audience engagement — with a level of autonomy you configure.

Think of it as a **creative twin**: it multiplies your fingerprint instead of replacing it.

### Services

- 🎬 **Automated video editing** — post / reels / shorts / TikTok / story (up to 5 minutes)
- 🖼️ **Image + text posts** — generated on-brand
- 💬 **Comment replies** — AI-automated, configurable
- 📨 **Direct messages** — automated or deterministic
- 📊 **Monitoring** — content and engagement performance

### Supported platforms

**YouTube** · **Meta** (Facebook, Instagram, Threads) · **TikTok** · **LinkedIn**

---

## What makes us different

- **On-brand at scale** — content that sounds like *you*, produced at volume.
- **Everywhere, adapted** — one idea, auto-tailored to each platform's format via a 20-format editing
  engine across 7 archetypes.
- **You're in control** — configurable autonomy: approve, edit, or fully automate.
- **Transparent by design** — clear usage, clear costs. No surprises (at-cost beta tier, pass-through).
- **Isolated multi-tenant** — per-tenant isolation (`tenant_id` + Postgres RLS), GDPR-ready.

---

## Platform & engineering

A polyrepo platform split into a **control plane** and a **data plane**, deployed continuously to a
self-hosted Kubernetes cluster.

| Repository | Role | Stack |
|---|---|---|
| `geminel-platform` | Control plane — accounts, billing (Stripe), service management | FastAPI · React · PostgreSQL |
| `geminel-smm` | Data plane — content engine, publishing, engagement (multi-tenant) | FastAPI · React · PostgreSQL · Qdrant |
| `geminel-gitops` | GitOps — ArgoCD app-of-apps, Helm/Kustomize | YAML · Helm |
| `geminel-infra` | Infrastructure as Code — k3s, Harbor, observability, Cloudflare | Terraform · Ansible |
| `geminel-docs` | Architecture, specs, business & branding | Markdown |

**Pipeline:** `GitHub Actions → Harbor → GitOps → ArgoCD → k3s`

**AI stack:** Gemini · Claude · GPT · Veo · voice cloning — metered transparently per tenant.

---

<div align="center">

🌐 **[geminel.studio](https://geminel.studio)**

*Create once. Show up everywhere.*

</div>
