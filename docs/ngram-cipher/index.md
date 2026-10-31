---
layout: page
title: N-Gram Cipher - Steganographic Encryption
parent: Documentation Hub
permalink: /docs/ngram-cipher/
---

# N-Gram Cipher: Natural English Steganographic Encryption

**`ngram-cipher`** is an open-source TypeScript and JavaScript steganography engine that encrypts secret payloads using **AES-256-GCM** and conceals the resulting ciphertext directly within losslessly reversible, grammatically natural English prose or poetic stanzas.

Instead of classical pixel- or audio-based steganography, `ngram-cipher` maps encrypted bitstreams into power-of-two continuation tokens guided by statistical 1–5 gram language models (derived from Google Books N-Gram datasets).

---

## ⚡ Interactive Live Cipher Tester

Test the library right now in your browser using the client-side JavaScript engine bundled directly on this site:

<div class="card" style="margin: 1.5rem 0; padding: 1.5rem; background: var(--bg-surface); border: 1px solid var(--border-subtle); border-radius: 8px;">
  <div style="margin-bottom: 1rem;">
    <label for="live-pass" style="font-weight: 600; display: block; margin-bottom: 0.4rem;">🔑 Secret Password / Key:</label>
    <input type="password" id="live-pass" value="ArkSecure2026!" style="width: 100%; padding: 0.6rem; border: 1px solid var(--border-subtle); border-radius: 6px; background: var(--bg-card); color: var(--text-color); font-size: 0.95rem;">
  </div>

  <div style="margin-bottom: 1rem;">
    <label for="live-plain" style="font-weight: 600; display: block; margin-bottom: 0.4rem;">📝 Plaintext to Encode:</label>
    <textarea id="live-plain" rows="3" style="width: 100%; padding: 0.6rem; border: 1px solid var(--border-subtle); border-radius: 6px; background: var(--bg-card); color: var(--text-color); font-size: 0.95rem;">Deploy the release bundle at midnight behind the embassy.</textarea>
  </div>

  <div style="margin-bottom: 1rem;">
    <label for="live-style" style="font-weight: 600; display: block; margin-bottom: 0.4rem;">🎨 Carrier Prose Style:</label>
    <select id="live-style" style="width: 100%; padding: 0.6rem; border: 1px solid var(--border-subtle); border-radius: 6px; background: var(--bg-card); color: var(--text-color); font-size: 0.95rem;">
      <option value="news">News Prose (Journalistic N-Gram LM)</option>
      <option value="poetry">Poetry (Dynamic Stanzas & Rhythm)</option>
    </select>
  </div>

  <div style="display: flex; gap: 0.8rem; margin-bottom: 1rem;">
    <button id="live-btn-encode" class="btn btn-primary" style="cursor: pointer; flex: 1;">🔒 Encode into Natural English</button>
    <button id="live-btn-decode" class="btn btn-secondary" style="cursor: pointer; flex: 1;">🔓 Decode back to Plaintext</button>
  </div>

  <div id="live-status" style="display: none; padding: 0.75rem; border-radius: 6px; margin-bottom: 1rem; font-size: 0.9rem;"></div>

  <div>
    <label for="live-cipher" style="font-weight: 600; display: block; margin-bottom: 0.4rem;">💬 English Carrier Ciphertext:</label>
    <textarea id="live-cipher" rows="5" placeholder="Encoded English carrier text will appear here..." style="width: 100%; padding: 0.6rem; border: 1px solid var(--border-subtle); border-radius: 6px; background: var(--bg-card); color: var(--text-color); font-size: 0.95rem;"></textarea>
  </div>
</div>

<script>
document.addEventListener("DOMContentLoaded", function() {
  const passEl = document.getElementById("live-pass");
  const plainEl = document.getElementById("live-plain");
  const cipherEl = document.getElementById("live-cipher");
  const styleEl = document.getElementById("live-style");
  const statusEl = document.getElementById("live-status");
  const encodeBtn = document.getElementById("live-btn-encode");
  const decodeBtn = document.getElementById("live-btn-decode");

  function showMsg(text, isError) {
    statusEl.style.display = "block";
    statusEl.style.backgroundColor = isError ? "rgba(239, 68, 68, 0.15)" : "rgba(34, 197, 94, 0.15)";
    statusEl.style.color = isError ? "#ef4444" : "#22c55e";
    statusEl.style.border = isError ? "1px solid #ef4444" : "1px solid #22c55e";
    statusEl.textContent = text;
  }

  encodeBtn.addEventListener("click", async function() {
    try {
      statusEl.style.display = "none";
      const cipherLib = window.ngramCipher;
      if (!cipherLib || !cipherLib.encode) {
        showMsg("Cipher engine library is not loaded.", true);
        return;
      }
      const plain = plainEl.value.trim();
      const pass = passEl.value;
      if (!plain || !pass) {
        showMsg("Please provide both plaintext and a password.", true);
        return;
      }
      const style = styleEl.value;
      const res = await cipherLib.encode(plain, pass, { encoding: { style: style } });
      cipherEl.value = res;
      showMsg("Successfully encoded into natural English prose!", false);
    } catch (err) {
      showMsg(err.message || String(err), true);
    }
  });

  decodeBtn.addEventListener("click", async function() {
    try {
      statusEl.style.display = "none";
      const cipherLib = window.ngramCipher;
      if (!cipherLib || !cipherLib.decode) {
        showMsg("Cipher engine library is not loaded.", true);
        return;
      }
      const cipher = cipherEl.value.trim();
      const pass = passEl.value;
      if (!cipher || !pass) {
        showMsg("Please provide ciphertext and a password.", true);
        return;
      }
      const style = styleEl.value;
      const res = await cipherLib.decode(cipher, pass, { encoding: { style: style } });
      plainEl.value = res;
      showMsg("Successfully decoded and verified plaintext!", false);
    } catch (err) {
      showMsg("Decryption failed: " + (err.message || "Invalid password or corrupted text."), true);
    }
  });
});
</script>

---

## 🔑 Key Architectural Features

1. **Robust Cryptography**:
   - Key derivation using **PBKDF2** with 100,000 SHA-256 iterations.
   - Symmetric authenticated encryption via **AES-256-GCM**.
   - Binary frame verification with CRC32 checksums and bit whitening.
2. **Natural Carrier Prose (News & Poetry)**:
   - Dynamic grammatical sentence construction prevents structural repetition within subsequent sentences.
   - Context continuation probabilities prevent unnatural keyword clustering.
3. **100% Losslessly Reversible**:
   - Power-of-two slot allocation guarantees bit-exact extraction without precision drift.
4. **Adaptive Compression**:
   - Transparent pre-encryption payload compression with `gzip` or common-word packing.

---

## 📦 Installation & Usage

Install the package via npm:

```bash
npm install ngram-cipher
```

### Modern ESM / TypeScript

```typescript
import { encode, decode } from "ngram-cipher";

// 1. Encode
const carrier = await encode("Classified update", "StrongPassword123");
console.log(carrier);

// 2. Decode
const plaintext = await decode(carrier, "StrongPassword123");
console.log(plaintext); // "Classified update"
```

### Browser Script Tag

Include the global build directly from our site or CDN:

```html
<script src="{{ '/assets/js/ngram-cipher.global.js' | relative_url }}"></script>
<script>
  window.ngramCipher.encode("My Secret", "password").then(console.log);
</script>
```

---

## 🔗 Project Links

* **GitHub Repository**: [https://github.com/3-ark/ngram-cipher](https://github.com/3-ark/ngram-cipher)
* **License**: MIT
