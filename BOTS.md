# Bots of Security  (docx S5 candidate menu)

These are the **Major sub-functions** of Security from the spec. Each is a bot — a
child decision system that can be instantiated to do the actual work.

## Install flow (matches the Orientation Protocol)
1. **Orient** — the agent runs the Kojiki Orientation Protocol (name / industry /
   jurisdiction / siblings).
2. **Research** — the agent researches the field and decides which sub-functions this
   specific org needs.
3. **Install** — instantiate only the chosen bots:
   ```bash
   cd bots
   python3 install_bots.py brand growth performance-marketing
   ```
   (use the slugs listed below; omit args to install all). Each installed bot becomes a
   full decision system under `bots/<slug>/` with README + AGENT.md + schemas + a stub
   decision record, and registers under this department's group_id for handoffs.

Total candidates: 7.

- `security-architecture` — **Security Architecture**  ·  titles: CISO, VP Security, Security Director, Security Engineering Manager, Security Engineer, SOC Analyst, Security Analyst, Incident Response Lead
- `cybersecurity` — **Cybersecurity**  ·  titles: CISO, VP Security, Security Director, Security Engineering Manager, Security Engineer, SOC Analyst, Security Analyst, Incident Response Lead
- `application-security` — **Application Security**  ·  titles: CISO, VP Security, Security Director, Security Engineering Manager, Security Engineer, SOC Analyst, Security Analyst, Incident Response Lead
- `cloud-security` — **Cloud Security**  ·  titles: CISO, VP Security, Security Director, Security Engineering Manager, Security Engineer, SOC Analyst, Security Analyst, Incident Response Lead
- `security-operations` — **Security Operations**  ·  titles: CISO, VP Security, Security Director, Security Engineering Manager, Security Engineer, SOC Analyst, Security Analyst, Incident Response Lead
- `incident-response` — **Incident Response**  ·  titles: CISO, VP Security, Security Director, Security Engineering Manager, Security Engineer, SOC Analyst, Security Analyst, Incident Response Lead
- `security-governance` — **Security Governance**  ·  titles: CISO, VP Security, Security Director, Security Engineering Manager, Security Engineer, SOC Analyst, Security Analyst, Incident Response Lead
