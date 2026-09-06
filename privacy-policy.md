# Privacy Policy for InsightPage

*Last Updated: March 2025*

InsightPage ("the Extension") is designed with a **100% Privacy-First and Local-First Architecture**. We believe your browsing history, research notes, and AI conversations belong exclusively to you.

This Privacy Policy explains how InsightPage protects your privacy, how data is processed locally on your device, and how external services interact with the extension.

---

## ⚡ At a Glance (Executive Summary)

| Privacy Guarantee | Policy & Practice |
| :--- | :--- |
| **Data Collection** | **Zero.** We do not track, collect, aggregate, store, or sell any personal data, search queries, notes, or browsing history. |
| **User Accounts & Login** | **None required.** No registration, no user profiles, and no developer servers or proxies. |
| **API Keys & Credentials** | Stored **locally in your browser** via standard extension storage. Never transmitted to us or any third party. |
| **Local Models** | **100% On-Device.** When using Ollama, LM Studio, or local hosts, no data leaves your local machine network. |
| **Cloud AI Models** | **Direct Client-to-API.** Requests are sent directly from your browser to your selected AI provider (OpenAI, Gemini, Groq, OpenRouter, or custom endpoint) using your own API key (Bring Your Own Key - BYOK). |
| **Local Vault Integration** | Notes are saved directly to standard `.md` files on your local hard drive via the Web File System Access API. |

---

## 1. Core Architecture & Privacy Principles

### No Middleman & Zero Developer Tracking
InsightPage operates entirely as a client-side extension. There are **no middleman backend servers**, **no telemetry/tracking beacons**, **no user analytics services**, and **no advertising identifiers**. We have no capability to see, read, or monetize your interactions or data.

### Local-First Data Storage
All extension settings, persona configurations, custom themes, chat histories, and embedding indexes are saved locally in your browser's extension storage (`chrome.storage.local` / `localforage`) or written directly to standard Markdown (`.md`) files in folders you choose on your device.

---

## 2. Processing Modes: Local vs. Cloud AI

InsightPage gives you complete control over where and how AI requests are processed:

| Feature / Aspect | Local Models (e.g., Ollama, LM Studio) | Cloud AI Providers (e.g., OpenAI, Gemini, Groq) |
| :--- | :--- | :--- |
| **Network Destination** | `http://localhost:...` (Local Device) | Direct HTTPS to official API endpoint |
| **Data Transmission** | Stays 100% on your device network | Transmitted directly to provider API |
| **API Key Required?** | Usually No | Yes (Bring Your Own Key / BYOK) |
| **Developer Involvement** | Zero | Zero (No developer proxy or middleman) |
| **Applicable Policy** | This Policy (100% Local) | Selected AI Provider's Privacy Policy |

### A. Local (On-Device) AI Models
When connected to local model servers (such as Ollama or LM Studio running on `localhost`), all text processing, vector embeddings, and generation happen **entirely on your local machine**. No data is sent over the internet.

### B. Cloud-Based AI Providers
When you configure cloud providers (OpenAI, Google Gemini, Groq, OpenRouter, or a custom LLM endpoint):
* **Data Sent:** Only the prompt context necessary to fulfill your immediate request (such as active tab text, user message, or selected notes).
* **Direct Communication:** Your browser communicates directly with the provider's HTTPS endpoint.
* **Your Control & Choice:** You supply your own API keys. You can add, edit, or remove providers at any time.
* **Third-Party Policies:** Your interactions with cloud AI services are governed by their respective privacy policies:
  * [OpenAI Privacy Policy](https://openai.com/policies/row-privacy-policy/)
  * [Google Gemini API Terms & Privacy](https://ai.google.dev/gemini-api/terms)
  * [Groq Privacy Policy](https://groq.com/privacy-policy/)
  * [OpenRouter Privacy Policy](https://openrouter.ai/privacy)

---

## 3. Browser Permissions Explained

InsightPage requests specific Chrome extension permissions to provide browser assistant features. Here is a clear explanation of why each permission is required:

| Permission | Purpose & Scope |
| :--- | :--- |
| `activeTab` | Allows the AI assistant to read text or extract content from the active webpage when you trigger Page Mode or open the Floating Assistant. |
| `tabs` | Enables page context extraction, active tab title detection, and opening notes or side panel tabs. |
| `storage` | Saves your settings, persona preferences, active theme, and chat histories locally on your device. |
| `sidePanel` | Displays the main InsightPage assistant interface in Chrome's native side panel. |
| `scripting` | Injects the lightweight floating action button into web pages when enabled in settings. |
| `offscreen` | Performs background PDF text parsing and embedding calculations efficiently without blocking the main UI thread. |
| `contextMenus` | Adds right-click context menu options (e.g., "Add to Note", "Add to Weekly Note"). |
| `downloads` | Enables exporting chat logs and notes as `.md`, `.json`, `.txt`, or `.pdf` files to your computer. |
| `notifications` | Displays subtle status updates (e.g., note saved or export completed). |
| `declarativeNetRequest` | Used for header adjustments needed during user-initiated web scraping or CORS compatibility for custom local endpoints. |

---

## 4. Web Search & Scraped Context

When you enable **Web Mode** (`/web` or Web Search button) or drag URLs into the chat context bar:
* **Live Search Queries:** Search queries are sent directly to the selected search engine (e.g., DuckDuckGo, Brave, Google, or Google Custom Search).
* **Page Scraping:** To summarize search results or referenced URLs, InsightPage fetches the public HTML content of target pages directly from your browser.
* **No Profiling:** Web searches are performed on-demand for the current query and are never logged or tracked by InsightPage.

---

## 5. Data Security, Retention & Deletion

* **Data Ownership:** You maintain 100% ownership of all your content, notes, and chat logs.
* **Exporting Data:** You can export your entire extension dataset as a `.zip` archive or individual notes/chats at any time via the Share menu.
* **Deleting Data:**
  * Clearing chat logs in the extension immediately removes them from `chrome.storage.local`.
  * Deleting notes removes them from your local directory or local extension vault.
  * Resetting settings or uninstalling the extension permanently deletes all extension storage from your browser.

---

## 6. Children's Privacy

InsightPage does not knowingly collect or solicit data from children under the age of 13. The extension is a general-purpose productivity tool that operates locally on the user's device.

---

## 7. Changes to This Privacy Policy

If we update this Privacy Policy to reflect new browser capabilities or features, the revised policy will be posted in this repository with an updated revision date.

---

## 8. Contact Us

If you have questions, feedback, or concerns regarding this Privacy Policy or InsightPage's privacy practices:
* **GitHub Repository:** Open an issue or discussion on our official repository.
