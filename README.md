markdown
# 🧨 Netflix Cookie Checker V4.5 | @DEVELOPER_RAIM

> Fast multi-threaded Netflix cookie checker with extra-member separation, on‑hold routing, NFToken generator, and Telegram/Discord alerts.

---

## 🔥 What’s New

- On‑hold accounts → `output/run_.../On Hold/<Plan>/`
- `OnHold` counter in console
- `add_emojis`: `false`, `"txt"`, `"webhook"`, `"both"`
- Better cookie parsing + hold‑status extraction

---

## ⚡ Features

- Multi‑threaded (fast)
- Supports `.txt` (Netscape) and `.json` cookies
- Extracts: plan, country, billing, streams, quality, payment, profiles, etc.
- **NFToken generation** – PC / mobile login links
- Proxy support (HTTP/HTTPS/SOCKS, auto‑rotate on retry)
- Duplicate filtering
- Output sorted by run folder and plan
- Discord & Telegram notifications (`full` / `cookie` / `nftoken`)
- Display modes: `log` (verbose) or `simple` (dashboard)
- Auto‑creates missing folders/config

---

## 📦 Requirements

```bash
pip install -r requirements.txt
```

For SOCKS proxies (optional):

```bash
pip install requests[socks]
```

---

🚀 Quick Start

1. Put cookie files (.txt / .json) into cookies/
2. (Optional) Add proxies to proxy.txt
3. Edit config.yml (set nftoken: "both" to get login links)
4. Run:

```bash
python main.py
```

---

📁 Output Structure

```
cookies/                      # place your cookie files here
output/
  run_YYYY-MM-DD_HH-MM-SS/
    Premium/
    Premium (Extra Member)/
    Standard/
    Standard With Ads/
    Basic/
    Mobile/
    Free/
    Duplicate/
    On Hold/
      Premium/
      Standard/
      Basic/
      Mobile/
    Unknown/                  # only if needed
failed/                       # invalid cookies
broken/                       # network errors / retry exhausted
proxy.txt
config.yml
```

---

🍪 Cookie Formats

Netscape (.txt)

```
.netflix.com  TRUE  /  TRUE  1234567890  NetflixId  xxx
.netflix.com  TRUE  /  TRUE  1234567890  SecureNetflixId  xxx
```

JSON (.json)

```json
[{"domain":".netflix.com","name":"NetflixId","value":"xxx"}]
```

---

🔌 Proxy Formats (one per line)

```
ip:port
user:pass@ip:port
http://ip:port
socks5://user:pass@ip:port
ip:port:user:pass
ip:port user:pass
ip:port|user:pass
```

---

⚙️ Minimal config.yml Example

```yaml
nftoken: "both"               # generates PC + mobile login links
add_emojis: "webhook"

notifications:
  telegram:
    enabled: true
    bot_token: "YOUR_BOT_TOKEN"
    chat_id: "YOUR_CHAT_ID"
    mode: "full"
    plans: "all"

display:
  mode: "simple"

retries:
  error_proxy_attempts: 4
  nftoken_attempts: 5
```

---

🔗 NFToken Links

· pc   → https://netflix.com/?nftoken=...
· mobile → https://netflix.com/unsupported?nftoken=...
· both → both links

---

📞 Contact

Telegram: @DEVELOPER_RAIM

---

⚠️ Disclaimer

Educational use only. Use only on accounts you own or have permission to test.
