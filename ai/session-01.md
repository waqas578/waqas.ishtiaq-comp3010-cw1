# AI use log — COMP3010 CW1

**Student:** Waqas Ishtiaq  
**Student numbers:** 20165616 (HKUSPACE) / 10966127 (University of Plymouth)  
**Purpose:** Record free / open AI assistance used during investigation and report drafting, plus human validation steps.

## Tools declared (free tier / open)

| Tool | Access | Role |
|---|---|---|
| Cursor Agent (student free / included IDE access) | Editor assistant | Wireshark filter wording, report structure, evidence checklist |
| Grok AI (free tier, browser/app) | Free account | Plain-English explanations of HTTP fields / IDS wording |
| Local notes only | N/A | Final quiz answers and hashes checked against PCAP/alerts by me |

No paid API keys, no paid Grok / xAI subscription, and no commercial closed paid API were used for the submitted artefacts described here.

---

## Session entries

### 1. Wireshark filter help
- **Date:** during CW1 practical analysis  
- **Prompt (summary):** How to filter HTTP host `unwrappedphotos.com` and find Referer in Wireshark.  
- **AI output:** Suggested `http.host=="unwrappedphotos.com"` and expanding the HTTP layer.  
- **My validation:** Applied filter on `COMP3010HK_CW1.pcap`; confirmed frame **14055**, Host and Google Referer myself.  
- **Accepted / rejected:** Accepted filter syntax; rejected any claim that local desktop time equals packet UTC without checking Frame arrival time.

### 2. Alert date confusion (Q5)
- **Prompt (summary):** What date is “Evil Redirector Leading to EK Jul 12 2016”?  
- **AI output:** Initially mixed event date (2016-10-14) with signature string date.  
- **My validation:** Re-read `CW1-alerts.txt` line; signature text is **Jul 12 2016** → answer **2016-07-12**; event time remains 2016-10-14 22:14:42 UTC.  
- **Accepted / rejected:** Rejected using only the PCAP calendar date for Q5; accepted signature date after alert file check.

### 3. Destination port (Q6)
- **Prompt (summary):** Infection destination port from Evil Redirector alert.  
- **AI output:** Sometimes suggested TCP/80 (server side).  
- **My validation:** Alert line shows `sport=80 -> dport=49450` for that event; report uses **49450** as the quiz/alert destination port; EK traffic continues on TCP/80.  
- **Accepted / rejected:** Rejected “only port 80” as the quiz answer without reading the alert; kept both facts clear in the report.

### 4. Campaign name (Q9)
- **Prompt (summary):** Campaign related to WordPress referrer-detector / Evil Redirector.  
- **AI output:** Discussed EITest vs PseudoDarkleech patterns.  
- **My validation:** Aligned final answer to module quiz key **PseudoDarkleech**; PCAP alone does not prove exclusive attribution (noted under uncertainty).  
- **Accepted / rejected:** Accepted PseudoDarkleech as the labelled campaign answer; rejected over-confident unique attribution.

### 5. Hash / export objects
- **Prompt (summary):** How to evidence payload size without saving malware to Desktop.  
- **AI output:** Use File → Export Objects → HTTP list; hash from reassembled streams.  
- **My validation:** Confirmed object sizes ~30 kB / 50 kB / 490 kB and Content-Length **490175** on frame **15099**; did not Save malware binaries for day-to-day use.  
- **Accepted / rejected:** Accepted method; rejected downloading/executing the payload.

### 6. Report structure (new brief)
- **Prompt (summary):** Upgrade report for methodology, uncertainty, NIST/NCSC/ISO recommendations.  
- **AI output:** Suggested §8 uncertainty rewrite and §9 strategic/operational recommendations.  
- **My validation:** Checked quiz facts still match; word count kept near 1000 for §§1–9; standards names verified as NIST SP 800-61, NCSC CAF, ISO/IEC 27035.  
- **Accepted / rejected:** Accepted structure; I own final wording and legal HK references.

### 7. Evidence portfolio layout
- **Prompt (summary):** What folders for a CW1 evidence Git repo.  
- **AI output:** `screenshots/`, `alerts/`, `hashes/`, `filters.md`, `ai/`.  
- **My validation:** Created repo myself; copied text artefacts; screenshots from my own Wireshark captures.  
- **Accepted / rejected:** Accepted layout; no full PCAP upload.

---

## Hallucinations / errors caught
1. Mixing **alert signature date** with **packet event date**.  
2. Treating **TCP/80** as the only port answer when the alert **dport** is **49450**.  
3. Over-stating campaign certainty beyond the PCAP.

## Validation rule used
A finding was kept only when **frame number / HTTP host / alert line / hash or size** agreed. AI text never replaced opening the PCAP or alert files.

## Limits
AI cannot see my live Wireshark GUI; it cannot invent correct hashes. Free-tier chat may truncate long PCAP discussions. Human review was required for quiz accuracy and for Appendix B screenshots.
