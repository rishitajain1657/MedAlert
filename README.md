# 🛡️ MedAlert — The Medicine Safety Detective
> **Deciphering official drug recalls and CDSCO substandard batch notices into plain-language consumer protection via TinyFish AI Web Agents.**

https://github.com/
https://github.com/
https://www.tinyfish.ai/
https://cdsco.gov.in/

---

## 🚨 The Invisible Hazard: India's Substandard Medicine Crisis

Every month, India's statutory drug regulatory authorities—the **Central Drugs Standard Control Organisation (CDSCO)** and State FDAs—routinely test commercial medicine samples across pharmacies and declare dozens of batches as **Not of Standard Quality (NSQ)**, adulterated, or spurious.

Commonly flagged medications include everyday essentials like **Paracetamol (Dolo/Crocin)**, **Telmisartan (Blood Pressure)**, **Pantoprazole (Antacids)**, and **Pediatric Cough Syrups**.

### The Citizen Information Vacuum
1. **Buried Scanned Gazettes**: Regulatory recalls are published as dense, non-searchable 40-page scanned PDFs on government websites with zero public notification mechanisms.
2. **Technical Laboratory Jargon**: Notices cite terms like *"Fails IP Dissolution test"* or *"Assay 68.2% against IP limits"*, leaving everyday citizens unable to evaluate clinical risk.
3. **The 30-Day Retail Lag**: Physical recall circulars take weeks to reach local retail chemists, meaning patients often consume unsafe batches before pharmacies receive notice.
4. **False Panic vs. Batch Reality**: When news outlets report *"Dolo flagged"*, patients panic and stop taking vital prescriptions, unaware that only a single manufacturing lot was defective while other batches remain completely safe.

---

## 💡 The Solution: MedAlert

MedAlert is an autonomous conversational medicine detective that bridges the gap between apex government drug circulars and ordinary citizens.

* **Zero-Friction Intake**: Citizens simply snap a smartphone photo of their medicine blister foil or type the Brand and Batch Number (e.g., `Dolo-650 #T24018`).
* **Autonomous Regulatory Crawl**: Powered by **TinyFish AI Web Agents**, MedAlert navigates dynamic, session-locked CDSCO and State FDA gazettes to extract batch recall data without relying on nonexistent government APIs.
* **Batch-Level Precision Engine**: Eliminates brand panic by evaluating the exact manufacturing lot against regulatory records.
* **Plain-Language Clinical Translation**: Converts technical lab assay failures into actionable consumer guidance (e.g., *"Tablet dissolves too slowly to provide fever relief"*).
* **Caregiver Escalation Loop**: Automatically notifies family members via WhatsApp if an elderly relative scans a recalled batch.

---

## ⚙️ Core Technical Moat: TinyFish Autonomous Web Agents

Apex regulators publish circulars across dynamic portals like [CDSCO](https://cdsco.gov.in/) and [Indian Pharmacopoeia Commission (IPC)](https://ipc.gov.in/) without public REST APIs or RSS feeds. Standard scrapers fail on session timeouts, dynamic JavaScript tables, and monthly layout changes.

### Why TinyFish is Essential
1. **Headless Browser Navigation**: TinyFish runs managed cloud Chromium sessions to autonomously traverse circular archives, bypass portal timeouts, and locate new monthly releases.
2. **Dynamic Table & PDF Extraction**: Normalizes unstandardized columns (Brand, Lot No, Manufacturer, Assay Failure Reason) into clean, structured JSON schemas.
3. **Zero Private API Dependency**: Enables immediate, functional public safety integration without waiting for government IT overhauls.

```json
{
  "agent_engine": "TinyFish Autonomous Web Agent v2.4",
  "auth_mode": "X-API-Key Authenticated",
  "data_source": "[https://api.search.tinyfish.ai](https://api.search.tinyfish.ai)",
  "verdict_tier": "TIER_1_CONFIRMED_BATCH_RECALL",
  "normalized_record": {
    "match_status": "CONFIRMED_ALERT",
    "drug_name": "Dolo-650 (Paracetamol Tablets IP 650mg)",
    "batch_number": "T24018",
    "manufacturer": "Micro Healthtech Laboratories",
    "failure_reason_lab": "Fails IP Dissolution test (<70% in 30 minutes)",
    "plain_language_impact": "The active fever-reducing chemical dissolves too slowly, causing therapeutic failure.",
    "circular_reference": "CDSCO/Alert/2026/09/NSQ-042"
  }
}
