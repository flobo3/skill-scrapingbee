---
name: scrapingbee-fetch
description: Fetch and render JavaScript-heavy or bot-protected websites using ScrapingBee API. Returns clean Markdown.
---

# ScrapingBee Fetch OSS

Use this skill to bypass bot protection (Cloudflare, DataDome, etc.) and render JavaScript on target websites. It extracts the main content and returns it as clean Markdown optimized for LLM reading.

## Setup

You need a ScrapingBee API key to use this skill. Set it as an environment variable:

```bash
export SCRAPINGBEE_API_KEY="your_api_key_here"
```

Or add it to a `.env` file in the directory where you run the script.

## Usage

```bash
uv run fetch.py --url "https://example.com"
```

## Optional Parameters

- `--no-render-js`: Disable JavaScript rendering (faster, but might miss dynamic content).
- `--country-code <code>`: Use a proxy from a specific country (e.g., `us`, `uk`, `ru`).
- `--wait <milliseconds>`: Wait time in milliseconds before extracting content (default: 3000).
- `--no-block-ads`: Disable ad blocking (ads are blocked by default to save bandwidth and speed up rendering).
- `--premium-proxy`: Use a premium proxy (useful for highly protected websites).

## Examples

Fetch a website using a US proxy and wait 5 seconds:
```bash
uv run fetch.py --url "https://example.com" --country-code us --wait 5000
```

Fetch a highly protected website using a premium proxy:
```bash
uv run fetch.py --url "https://example.com" --premium-proxy
```

Fetch a simple website without rendering JavaScript:
```bash
uv run fetch.py --url "https://example.com" --no-render-js
```
