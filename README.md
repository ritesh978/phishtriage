# 🎣 PhishTriage

> Open-source, client-side phishing email analyzer. Drop in an `.eml` file, get an instant threat report — no server, no data upload, no tracking.

![License](https://img.shields.io/badge/license-MIT-green) ![Version](https://img.shields.io/badge/version-2.0-blue) ![No Backend](https://img.shields.io/badge/backend-none-brightgreen)

---

## 🔍 What it does

PhishTriage parses raw email files (`.eml`) entirely in the browser and produces a structured phishing risk assessment in seconds.

**Analysis includes:**
- **Phishing score** (0–100) with weighted risk factors
- **Email authentication** — SPF, DKIM, and DMARC result parsing
- **IOC extraction** — URLs, domains, and IP addresses
- **Typosquatting detection** — flags domains impersonating known brands (PayPal, Google, Microsoft, etc.)
- **Attachment analysis** — identifies risky file extensions with simulated MD5 hashes
- **VirusTotal integration** — optional real-time URL reputation scanning (free API key supported)
- **Incident ticket generation** — copy-ready Markdown report for SOC workflows
- **JSON case file export** — structured output for SIEM or further processing

---

## 🚀 Live Demo

👉 **[Try it here](https://ritesh978.github.io/phishtriage)**

No install. No signup. Just drop an `.eml` file.

---

## 📸 Screenshot

> *(Add a screenshot of the results panel here)*
>
> ### 🎥 Demo Video

<video src="https://github.com/ritesh978/phishtriage/blob/main/assets/tooldemo.mp4.webm?raw=true" controls></video>


---

## 🛠️ How to use

### Option 1 — Use the live demo
Visit the link above and drag-and-drop any `.eml` file.

### Option 2 — Run locally
```bash
git clone https://github.com/YOUR_USERNAME/phishtriage.git
cd phishtriage
# Open index.html in your browser — no build step needed
open index.html
```

### VirusTotal API (optional)
1. Get a free API key at [virustotal.com](https://www.virustotal.com)
2. Click **VT API** in the top-right corner of the tool
3. Paste your key — it's stored only in your browser's memory

> Free tier supports scanning up to 4 URLs/minute. The tool handles rate limiting automatically.

---

## 🧠 How the scoring works

Each email is scored out of 100 based on weighted risk signals:

| Signal | Weight |
|---|---|
| SPF / DKIM / DMARC failures | High |
| Suspicious sender domain | High |
| Typosquatting detected | High |
| IP address in URL | Medium |
| URL shortener used | Medium |
| Urgency keywords in subject | Medium |
| Reply-To mismatch | Medium |
| Risky attachment extension | High |
| Suspicious X-Mailer header | Low |

Scores map to verdicts: **CLEAN → SUSPICIOUS → LIKELY PHISHING → PHISHING**

---

## 🔒 Privacy

**Everything runs in your browser.** No email content is ever sent to a server (unless you opt into VirusTotal scanning). You can disconnect from the internet and it will still work.

---

## 🗂️ Project structure

```
phishtriage/
└── index.html      # Entire app — HTML, CSS, and JS in one file
```

---

## 💡 Use cases

- SOC analysts triaging suspicious emails
- Security awareness training demos
- CTF / blue team practice
- Learning email authentication (SPF/DKIM/DMARC)

---

## 🤝 Contributing

Contributions welcome! Ideas for improvement:

- [ ] MIME multipart parsing for complex `.eml` files
- [ ] Expanded brand list for typosquatting detection
- [ ] VirusTotal file hash lookup for attachments
- [ ] Dark/light theme toggle
- [ ] Bulk analysis (multiple files)

Open an issue or submit a PR.

---

## 📄 License

MIT — free to use, modify, and distribute.

---

*Built with vanilla HTML, CSS, and JavaScript. No frameworks. No dependencies. No nonsense.*
