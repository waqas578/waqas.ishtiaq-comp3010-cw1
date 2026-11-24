# COMP3010 CW1 Evidence Portfolio

**Student:** Waqas Ishtiaq  
**Student number:** 20165616 (HKUSPACE) / 10966127 (University of Plymouth)  
**Module:** COMP3010 Security Operations and Incident Management  
**Assessment:** Coursework 1 — intrusion analysis (Cerber drive-by)

This repository holds technical evidence for my investigation of `COMP3010HK_CW1.pcap` and the related alert logs. The full PCAP is **not** uploaded here; integrity is shown via hashes in `/hashes`.

**Evidence portfolio URL:** https://github.com/waqas578/waqas.ishtiaq-comp3010-cw1

## Repository layout

```text
README.md
filters.md
alerts/
  evil-redirector-excerpt.txt
  rig-cerber-excerpt.txt
hashes/
  hashes.md
  other-indicators.md
screenshots/
  (Wireshark / alert screenshots B1–B8)
ai/
  session-01.md   (AI prompt log and validation notes)
```

## Contents

| Path | What it is |
|---|---|
| `alerts/evil-redirector-excerpt.txt` | Evil Redirector Leading to EK (signature date 2016-07-12; event 2016-10-14 22:14:42 UTC; `50.56.223.21:80 → 10.14.106.192:49450`) |
| `alerts/rig-cerber-excerpt.txt` | RIG landing/exploit related alerts and Cerber check-in (UDP/6892) |
| `hashes/hashes.md` | Landing page / Flash / payload MD5 + SHA-256 and sizes |
| `hashes/other-indicators.md` | Victim ID, Bitcoin address, UDP 6892, hosts |
| `filters.md` | Wireshark display filters used for screenshots 1–8 |
| `screenshots/` | Annotated tool outputs supporting the report |
| `ai/` | AI use log (prompts, acceptance/rejection, validation) |

## Notes

- Timestamps in the investigation are reported in **UTC**.
- Analysis was read-only; the payload was **not** executed.
- Source artefacts: `COMP3010HK_CW1.pcap`, `CW1-alerts.txt`, `CW1-alert-details.txt`.
