\# B2B Tech-Stack, DNS Security \& AI/LLM Readiness Auditor



Enrich thousands of B2B domains in seconds without slow headless browsers or expensive residential proxies. This lightweight, HTTP-only Actor inspects any company domain to extract its technology stack, marketing pixels, email provider, DNS security posture (`SPF` / `DMARC`), and \*\*AI/LLM search readiness\*\* (`llms.txt`, AI bot rules in `robots.txt`, and `JSON-LD` structured data).



Built specifically for \*\*B2B lead enrichment pipelines (n8n, Make, Clay)\*\* and \*\*autonomous AI agents via the Apify MCP Server\*\*.



\---



\## Key Features



\- \*\*AI \& LLM Readiness Audit (0–100 Score):\*\*

&#x20; - Checks for `/llms.txt` and validates that it returns real text rather than an HTML fallback.

&#x20; - Parses `/robots.txt` for specific AI crawler directives (`GPTBot`, `OAI-SearchBot`, `ChatGPT-User`, `ClaudeBot`, `PerplexityBot`, `Google-Extended`, `CCBot`, `Bytespider`).

&#x20; - Extracts `JSON-LD` / Schema.org types and SEO metadata (`title`, `meta description`).

\- \*\*Tech Stack \& Marketing Pixel Detection:\*\*

&#x20; - Detects e-commerce platforms \& CMS (`Shopify`, `WooCommerce`, `WordPress`, `Webflow`, `Framer`, `Next.js`).

&#x20; - Detects payment processors (`Stripe`, `Paddle`, `Polar.sh`), analytics (`GA4`, `GTM`, `PostHog`, `Plausible`), ad pixels (`Meta Pixel`, `LinkedIn Insight`), and CRM/support tools (`Klaviyo`, `HubSpot`, `Intercom`, `Crisp`, `Zendesk`).

&#x20; - Identifies CDN and hosting providers from HTTP response headers (`Cloudflare`, `Vercel`, `Netlify`).

\- \*\*Email \& DNS Security Intelligence:\*\*

&#x20; - Resolves `MX` records to identify the company's email provider (`Google Workspace`, `Microsoft 365`, `Zoho Mail`, `Proton Mail`).

&#x20; - Checks `SPF` (`v=spf1`) and `\_dmarc` (`p=none | quarantine | reject`) records for outbound email deliverability and domain security.

\- \*\*Fair Pay-Per-Event Pricing:\*\*

&#x20; - You are charged \*\*only\*\* when a domain is successfully fetched and enriched. Unreachable, invalid, or timed-out domains are skipped at \*\*$0.00\*\* cost.



\---

---

## Connect as an MCP Server (Claude, ChatGPT, Cursor)

This Actor works out-of-the-box with the official **Apify MCP Server** so AI agents can audit domains on demand.

### Option 1: Remote MCP URL (Claude.ai / Custom Connectors)
Add this URL as a custom connector and authorize with your Apify account:

```text
[https://mcp.apify.com?tools=carlitossrb/domain-intel-ai-auditor](https://mcp.apify.com?tools=carlitossrb/domain-intel-ai-auditor)

\## Example Output (JSON)



```json

{

&#x20; "success": true,

&#x20; "domain": "linear.app",

&#x20; "finalUrl": "\[https://linear.app/](https://linear.app/)",

&#x20; "auditedAt": "2026-11-20T13:25:10.412Z",

&#x20; "aiReadiness": {

&#x20;   "score": 80,

&#x20;   "hasLlmsTxt": true,

&#x20;   "hasRobotsTxt": true,

&#x20;   "blockedAiBots": \[],

&#x20;   "allowedAiBots": \[

&#x20;     "GPTBot",

&#x20;     "OAI-SearchBot",

&#x20;     "ChatGPT-User",

&#x20;     "ClaudeBot",

&#x20;     "Claude-Web",

&#x20;     "PerplexityBot",

&#x20;     "Google-Extended",

&#x20;     "CCBot",

&#x20;     "Bytespider"

&#x20;   ],

&#x20;   "hasJsonLd": false,

&#x20;   "jsonLdTypes": \[]

&#x20; },

&#x20; "techStack": \[

&#x20;   { "name": "Next.js", "category": "Framework" },

&#x20;   { "name": "Cloudflare", "category": "CDN / Security" }

&#x20; ],

&#x20; "techNames": \["Next.js", "Cloudflare"],

&#x20; "dnsSecurity": {

&#x20;   "emailProvider": "Google Workspace",

&#x20;   "mxRecords": \["aspmx.l.google.com"],

&#x20;   "hasSpf": true,

&#x20;   "hasDmarc": true,

&#x20;   "dmarcPolicy": "reject"

&#x20; },

&#x20; "seo": {

&#x20;   "title": "Linear – Plan and build products",

&#x20;   "metaDescription": "Linear streamlines issues, projects, and product roadmaps."

&#x20; }

}

