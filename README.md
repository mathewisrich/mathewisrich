# Mathew Sekanjako — Founder. Builder.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://linkedin.com/in/sekanjako-mathew)
[![Email](https://img.shields.io/badge/Email-EA4335?style=flat-square&logo=gmail&logoColor=white)](mailto:sekanjakomathew3.0@gmail.com)
[![Peechz](https://img.shields.io/badge/Peechz-FF6B6B?style=flat-square&logo=vercel&logoColor=white)](https://peechz.com)
[![Psalms23Wave](https://img.shields.io/badge/Psalms23Wave-000000?style=flat-square&logo=react&logoColor=white)](https://www.psalms23wave.com)

> TypeScript · Python · React Native · Next.js · Supabase · FastAPI · AI/ML
> **I ship products that real people use.** From a national government platform in Ghana, to a university in Ohio, to couples on the iOS App Store.

---

## Try What I've Built

**[▶️ Peechz — the video platform I'm building](https://peechz.com)**

---

## Traction That Matters

| Signal | Why it's rare |
|---|---|
| 🌍 **Government-Commissioned** | **CILGD** — National membership operating system built directly for Hon. Felix Mensah Nii Anang-La, former Mayor of Tema & former NALAG President, Ghana. |
| 📱 **iOS App Store — 11.4%** | **P31** — Live on the App Store with an 11.4% organic impression-to-download conversion rate (industry average is 2–5%). |
| 🏛️ **University Deployment** | **AkademData** — Running live at Mount Vernon Nazarene University. Processing 4,600 enrollment records for 2,700 students with zero parse errors. |
| 🥇 **Ohio Hackathon 2025** | **Most Original Product** — Peechz, winning against AI tooling, social platforms, and dev infra. |
| 🤖 **AI/ML Research** | **Alkebulan AI** — Fine-tuned Mistral-7B for five Ugandan languages (Luganda, Iteso, Runyankore, Acholi, Ateso). Published on HuggingFace. |

---

## The Work & How I Think

### [Peechz — Pitch. Match. Build.](https://peechz.com)
Short-form video pitch platform that replaces the tech resume. A custom AI routing engine matches builders directly with recruiters and investors.
👉 **[Read the Full Architecture Case Study](https://github.com/mathewisrich/Peechz-Architecture)**

> **The PTCHD Metric:** I rejected vanity views. A pitch is only counted as "PTCHD" when someone watches at least 50% of it or takes a high-intent action (saving/commenting) — optimizing for meaningful attention.
> **How the AI works:** I built the **Sekan Algorithm** as a 3-layer hybrid routing system: a Searcher generates discovery metadata, a Detector records behavioral signals (watch depth/actions), and a Recommender ranks feeds deterministically to avoid LLM latency.
> **Why it's hard:** Real-time video feeds are a distributed systems problem; counts, matches, and chat must sync without creating an API storm.
> **How I solved it:** I used singleton client managers with 30-second batch flushing to **eliminate ~95% of API chatter**. Postgres `AFTER INSERT OR DELETE` triggers with `SECURITY DEFINER` functions — plus a `supabase_realtime` publication — keep counts atomic and the UI live under concurrent load, with zero application-layer counter sync.

**Stack:** Next.js 15 · TypeScript · FastAPI (Python) · Supabase Realtime · Cloudflare R2 · Groq AI (Llama 3.3 + GPT-OSS 20B)

---

### [P31 — Proverbs 31 Christian Couples App](https://apps.apple.com/us/app/p31/id6759008572)
Faith-grounded mobile app featuring real-time ephemeral voice walkie-talkies and shared offline Bible integration.

> **Why it's hard:** Enforcing a strict 1-to-1 relationship in a multi-tenant database usually requires complex JOINs or heavy middleware.
> **How I solved it:** I embedded a shared `coupleid` UUID directly into the users table upon pairing, making the RLS policy a single line across the entire database:

```sql
-- My Zero-JOIN RLS policy used across every table in P31.
-- Because coupleid lives on users, this one line scales securely without JOINs.
(coupleid = (SELECT coupleid FROM users WHERE id = auth.uid()))
```

**Stack:** React Native · Expo SDK 54 · Supabase · TenTap · SQLite

---

### [CILGD — Chartered Institute of Local Governance and Development](https://cilgd.org)
Digital operating system for Ghana's premier local governance professional institute, replacing paper forms and WhatsApp workflows with a mobile-first platform.

> **Why it's hard:** Synchronizing payment-gateway onboarding with mid-year proration logic and national "good-standing" compliance requirements.
> **How I solved it:** Fully implemented **Paystack with HMAC SHA-512 webhook verification**. Built a multi-grade architecture where membership privileges are derived entirely via server-side database triggers, preventing client-side tampering.

**Stack:** React Native · Supabase · Next.js · Paystack

---

### AkademData — University Enrollment Analytics
👉 **[GitHub Repo](https://github.com/mathewisrich/akademdata-open-source)** · 📦 **[NPM Package](https://www.npmjs.com/package/akademdata-open-source)**

Drag-and-drop Excel ingestion pipeline that parses complex IPEDS, HLC, ODHE, and NC-SARA compliance formats without preprocessing.

> **Impact:** Saves 20–40 hours/month of manual Excel compliance work per institution. $0 licensing vs. $10K–$70K/yr incumbents.

**Stack:** ExcelJS · Prisma · SQLite · Node.js · React

---

### [Alkebulan AI — Indigenous Language Model](https://huggingface.co/Psalms23Wave/Alkebulan-AI)
Fine-tuned Mistral-7B for five under-resourced Ugandan languages: **Luganda, Iteso, Runyankore, Acholi, and Ateso.** Trained on parallel English↔local datasets for translation and basic interaction.

> **Research Focus:** Morphological analysis, syllable distribution, and OOV rate optimization for agglutinative Bantu syntax. Training on RunPod RTX A6000 and Google Cloud T4/A100 GPUs.

**Stack:** HuggingFace Transformers · PEFT · bitsandbytes · Datasets · SentencePiece

---

## Tech Stack
**Languages:** TypeScript, Python, SQL, JavaScript, Java, C++
**Frontend/Mobile:** React, Next.js 15, React Native, Expo SDK 54, Tailwind CSS
**Backend:** FastAPI, Node.js, Prisma
**Data/Infra:** PostgreSQL, Supabase (Auth/Realtime/Storage), Cloudflare R2, CDN
**AI/ML:** Groq API, HuggingFace, QLoRA, SentencePiece, Mistral-7B
**Payments:** Paystack

---

## Currently
- **Education:** BS in Cybersecurity & Master's coursework in IT Management at Mount Vernon Nazarene University (May 2026). Previously studied Electrical & Electronics Engineering, Mathematics, and Physics at Eastern Nazarene College.
- **Building:** Pushing Peechz toward full launch and P31 Android build.
- **Open to:** Founding engineer roles, YC Summer 2026 Batch, and high-impact technical consulting.

---

## Let's Build Something
I reply to people who want to ship fast.
- **Email:** [sekanjakomathew3.0@gmail.com](mailto:sekanjakomathew3.0@gmail.com)
- **LinkedIn:** [sekanjako-mathew](https://linkedin.com/in/sekanjako-mathew)
- **Company:** [Psalms23Wave LLC](https://www.psalms23wave.com)

*Through Christ Jesus I am made a Child of God. I build to serve.*
