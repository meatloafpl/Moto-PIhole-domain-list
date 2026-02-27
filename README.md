Moto Pi-hole Domain List

A supplementary blocklist for Pi-hole, built from real traffic analysis and OISD Big database filtering.

---

## Lists

### `/list` — Manual traffic analysis
Contains domains that slipped through currently implemented filters, captured on a Motorola device used as a test client.  
All captured domains were passed to an AI model, which selected those qualifying as **tracking / advertising / marketing** related. These were then used to enrich the list.

### `/additional` — OISD Big unique domains
Contains unique records filtered from the **OISD Big** database using a diff script.  
The script ensures that entries **do not duplicate** records already present in the base filters listed below.

> **Credit & Attribution**  
> The `/additional` list is derived from [OISD](https://oisd.nl) — a well-maintained, high-quality blocklist project by [@sjhgvr](https://github.com/sjhgvr).  
> OISD offers multiple variants including:
> - [Basic](https://basic.oisd.nl) — lightweight, low false-positive rate  
> - [Big](https://big.oisd.nl) — comprehensive, recommended for most users  
> - [NSFW](https://nsfw.oisd.nl) — adult content blocking  
>
> If you find OISD useful, consider using it directly or supporting the project at [oisd.nl](https://oisd.nl).  
> This repository does **not** claim ownership of any OISD content — we only redistribute a filtered subset to avoid duplication with other common lists.

---

## Base filters used

These lists serve as the deduplication baseline for `/additional`:

```
https://raw.githubusercontent.com/StevenBlack/hosts/master/hosts
https://raw.githubusercontent.com/hagezi/dns-blocklists/main/domains/pro.plus.txt
https://raw.githubusercontent.com/MajkiIT/polish-ads-filter/master/polish-pihole-filters/hostfile.txt
```

---

## Usage

Add the raw URLs of `/list` and `/additional` as adlists in your Pi-hole admin panel, then update gravity.
run `pihole -g` on your device after every configuration update.
