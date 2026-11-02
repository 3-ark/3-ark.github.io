---
layout: page
title: N-Gram Cipher - Steganographic Encryption
parent: Documentation Hub
permalink: /docs/ngram-cipher/
---

# 🔏 Natural English N-Gram Cipher

**`ngram-cipher`** is an open-source TypeScript & JavaScript steganography engine that encrypts secret payloads using **AES-256-GCM** and conceals the resulting ciphertext directly within losslessly reversible, grammatically natural English prose, poetry, or ONNX neural language model tokens.

---

## ⚡ Interactive Cipher Encoder & Decoder

Test the cipher engine directly in your browser. Select your preferred carrier style below—from statistical news prose and poetry stanzas to experimental causal language models:

<div class="card cipher-tester-card" style="margin: 1.75rem 0 2.5rem 0; padding: 1.75rem; border: 1px solid var(--border-color); border-radius: 14px; background: var(--bg-card); box-shadow: var(--card-shadow);">
  <div style="margin-bottom: 1.25rem;">
    <label for="cipher-password" style="display: block; font-weight: 700; margin-bottom: 0.5rem; font-size: 0.95rem; color: var(--text-main);">🔑 Secret Password / Key</label>
    <input type="password" id="cipher-password" value="MySecretKey123" placeholder="Enter encryption password..." style="width: 100%; padding: 0.75rem 1rem; border: 1px solid var(--border-color); border-radius: 8px; font-size: 0.95rem; background: var(--bg-body); color: var(--text-main); box-sizing: border-box; font-family: inherit;">
  </div>

  <div style="margin-bottom: 1.25rem;">
    <label for="cipher-plaintext" style="display: block; font-weight: 700; margin-bottom: 0.5rem; font-size: 0.95rem; color: var(--text-main);">📝 Plaintext Message</label>
    <textarea id="cipher-plaintext" rows="3" placeholder="Type message to encode..." style="width: 100%; padding: 0.75rem 1rem; border: 1px solid var(--border-color); border-radius: 8px; font-size: 0.95rem; background: var(--bg-body); color: var(--text-main); resize: vertical; box-sizing: border-box; font-family: inherit;">Hello world! This secret message will be encoded into natural English text.</textarea>
  </div>

  <div style="margin-bottom: 1.25rem;">
    <label for="cipher-style" style="display: block; font-weight: 700; margin-bottom: 0.5rem; font-size: 0.95rem; color: var(--text-main);">🎨 Carrier Writing Style</label>
    <select id="cipher-style" style="width: 100%; padding: 0.75rem 1rem; border: 1px solid var(--border-color); border-radius: 8px; font-size: 0.95rem; background: var(--bg-body); color: var(--text-main); box-sizing: border-box; font-family: inherit;">
      <option value="news">News prose (Google N-Gram Statistical LM)</option>
      <option value="poetry">Poetry (Dynamic Stanzas & Rhythm)</option>
      <option value="llm">LLM ONNX Mode (Transformers.js)</option>
      <option value="equal-length">Equal-Length Cipher LLM Mode (Norelli & Bronstein, 2025)</option>
    </select>
  </div>

  <!-- LLM Configuration Panel -->
  <div id="llm-panel" style="display: none; background: var(--bg-code); border: 1px solid var(--border-color); border-radius: 10px; padding: 1.25rem; margin-bottom: 1.25rem;">
    <div style="margin-bottom: 1rem;">
      <label for="llm-model" style="display: block; font-weight: 600; font-size: 0.9rem; margin-bottom: 0.35rem; color: var(--text-main);">Hugging Face Model ID or URL</label>
      <input type="text" id="llm-model" value="onnx-community/Supra-Mini-v2-0.1M-ONNX" placeholder="e.g. onnx-community/Supra-Mini-v2-0.1M-ONNX" style="width: 100%; padding: 0.65rem 0.85rem; border: 1px solid var(--border-color); border-radius: 6px; font-size: 0.9rem; background: var(--bg-card); color: var(--text-main); box-sizing: border-box; font-family: inherit;">
      <small style="color: var(--text-muted); display: block; margin-top: 0.35rem; font-size: 0.8rem;">
        Accepts model IDs (e.g. <code>onnx-community/Supra-Mini-v2-0.1M-ONNX</code>) or Hugging Face URLs. Model downloads directly on first run and caches in IndexedDB.
      </small>
    </div>

    <div id="llm-std-fields">
      <div style="margin-bottom: 1rem;">
        <label for="llm-prompt" style="display: block; font-weight: 600; font-size: 0.9rem; margin-bottom: 0.35rem; color: var(--text-main);">Generation Prompt Context</label>
        <input type="text" id="llm-prompt" value="In recent news," placeholder="Prompt context for model generation" style="width: 100%; padding: 0.65rem 0.85rem; border: 1px solid var(--border-color); border-radius: 6px; font-size: 0.9rem; background: var(--bg-card); color: var(--text-main); box-sizing: border-box; font-family: inherit;">
      </div>

      <div style="margin-bottom: 0.5rem;">
        <label for="bits-per-token" style="display: block; font-weight: 600; font-size: 0.9rem; margin-bottom: 0.35rem; color: var(--text-main);">Bits Embedded Per Token (1–8 bits)</label>
        <input type="number" id="bits-per-token" min="1" max="8" value="4" style="width: 100%; padding: 0.65rem 0.85rem; border: 1px solid var(--border-color); border-radius: 6px; font-size: 0.9rem; background: var(--bg-card); color: var(--text-main); box-sizing: border-box; font-family: inherit;">
      </div>
    </div>

    <div id="llm-equal-length-fields" style="display: none;">
      <div style="margin-bottom: 1rem;">
        <label for="equal-key-prompt" style="display: block; font-weight: 600; font-size: 0.9rem; margin-bottom: 0.35rem; color: var(--text-main);">Secret Key Prompt Context</label>
        <input type="text" id="equal-key-prompt" value="Here is an interesting observation:" placeholder="Secret key prompt context for cover text generation" style="width: 100%; padding: 0.65rem 0.85rem; border: 1px solid var(--border-color); border-radius: 6px; font-size: 0.9rem; background: var(--bg-card); color: var(--text-main); box-sizing: border-box; font-family: inherit;">
      </div>

      <div style="margin-bottom: 0.5rem;">
        <label for="equal-plain-prompt" style="display: block; font-weight: 600; font-size: 0.9rem; margin-bottom: 0.35rem; color: var(--text-main);">Plaintext Prompt Context</label>
        <input type="text" id="equal-plain-prompt" value="A text:" placeholder="Prompt context for plaintext distribution mapping" style="width: 100%; padding: 0.65rem 0.85rem; border: 1px solid var(--border-color); border-radius: 6px; font-size: 0.9rem; background: var(--bg-card); color: var(--text-main); box-sizing: border-box; font-family: inherit;">
      </div>
    </div>

    <div class="callout callout-warning" style="margin-top: 1rem; margin-bottom: 0; font-size: 0.85rem;">
      <div class="callout-title" style="font-weight: 700; color: #b45309;">⚠️ CRITICAL WARNING: LLM steganography methods are experimental.</div>
      <p style="margin: 0.4rem 0 0.5rem 0;">Decoding relies on bit-identical logit ranks. Even micro-deviations in floating-point math can alter token ranks and corrupt decoding. The following must match identically between encoding and decoding:</p>
      <ul style="margin: 0 0 0 1.2rem; padding: 0;">
        <li><strong>Runtime hardware & platform:</strong> Must use the same CPU architecture/SIMD/WASM execution provider.</li>
        <li><strong>Model checkpoint & precision:</strong> Exact model weights, repository, revision, and quantization.</li>
        <li><strong>Library versions:</strong> Exact <code>@huggingface/transformers</code> & ONNX Runtime versions.</li>
        <li><strong>Prompts & configuration:</strong> Generation prompts, key prompts, bits per token, and sampling settings.</li>
      </ul>
    </div>
  </div>

  <div id="cipher-status" style="display: none; padding: 0.85rem 1rem; border-radius: 8px; margin-bottom: 1.25rem; font-size: 0.9rem; font-weight: 500;"></div>

  <div id="cipher-error" style="display: none; padding: 0.85rem 1rem; border-radius: 8px; margin-bottom: 1.25rem; font-size: 0.9rem; font-weight: 500; background-color: rgba(239, 68, 68, 0.12); color: #ef4444; border: 1px solid rgba(239, 68, 68, 0.3);"></div>

  <div class="btn-group" style="display: flex; gap: 0.75rem; margin-bottom: 1.5rem; flex-wrap: wrap;">
    <button id="cipher-encode-btn" class="btn btn-primary" style="flex: 1; min-width: 200px; cursor: pointer; border: none; padding: 0.75rem 1.25rem;">🔒 Encode to English Prose</button>
    <button id="cipher-decode-btn" class="btn btn-secondary" style="flex: 1; min-width: 200px; cursor: pointer; padding: 0.75rem 1.25rem;">🔓 Decode to Plaintext</button>
  </div>

  <div>
    <div style="display: flex; justify-content: space-between; align-items: baseline; margin-bottom: 0.5rem;">
      <label for="cipher-ciphertext" style="font-weight: 700; font-size: 0.95rem; color: var(--text-main);">💬 English Carrier Ciphertext</label>
      <button id="cipher-copy-btn" style="background: none; border: 1px solid var(--border-color); color: var(--accent-primary); border-radius: 6px; padding: 0.2rem 0.6rem; font-size: 0.8rem; cursor: pointer; font-weight: 600;">📋 Copy</button>
    </div>
    <textarea id="cipher-ciphertext" rows="5" placeholder="Encoded English ciphertext will appear here..." style="width: 100%; padding: 0.75rem 1rem; border: 1px solid var(--border-color); border-radius: 8px; font-size: 0.95rem; background: var(--bg-body); color: var(--text-main); resize: vertical; box-sizing: border-box; font-family: inherit;"></textarea>
  </div>

  <div id="cipher-metrics" style="display: none; margin-top: 1rem; padding: 0.85rem 1rem; background: var(--bg-code); border: 1px solid var(--border-color); border-radius: 8px; font-size: 0.85rem; color: var(--text-muted); justify-content: space-between; flex-wrap: wrap; gap: 0.5rem;">
    <span>Words: <strong id="metric-words" style="color: var(--text-main);">0</strong></span>
    <span>Sentences: <strong id="metric-sentences" style="color: var(--text-main);">0</strong></span>
    <span>Avg Words/Sentence: <strong id="metric-avg-len" style="color: var(--text-main);">0</strong></span>
    <span>Vocabulary Coverage: <strong id="metric-vocab-cov" style="color: var(--text-main);">0%</strong></span>
  </div>
</div>

<script>
document.addEventListener("DOMContentLoaded", function() {
  const plainEl = document.getElementById("cipher-plaintext");
  const cipherEl = document.getElementById("cipher-ciphertext");
  const passEl = document.getElementById("cipher-password");
  const styleEl = document.getElementById("cipher-style");
  const llmPanelEl = document.getElementById("llm-panel");
  const llmModelEl = document.getElementById("llm-model");
  const llmPromptEl = document.getElementById("llm-prompt");
  const bitsPerTokenEl = document.getElementById("bits-per-token");
  const llmStdFieldsEl = document.getElementById("llm-std-fields");
  const llmEqualLengthFieldsEl = document.getElementById("llm-equal-length-fields");
  const equalKeyPromptEl = document.getElementById("equal-key-prompt");
  const equalPlainPromptEl = document.getElementById("equal-plain-prompt");
  const encodeBtn = document.getElementById("cipher-encode-btn");
  const decodeBtn = document.getElementById("cipher-decode-btn");
  const copyBtn = document.getElementById("cipher-copy-btn");
  const statusEl = document.getElementById("cipher-status");
  const errorEl = document.getElementById("cipher-error");
  const metricsEl = document.getElementById("cipher-metrics");
  const metricWords = document.getElementById("metric-words");
  const metricSentences = document.getElementById("metric-sentences");
  const metricAvgLen = document.getElementById("metric-avg-len");
  const metricVocabCov = document.getElementById("metric-vocab-cov");

  function updateStyleUI() {
    const style = styleEl.value;
    if (style === "llm") {
      llmPanelEl.style.display = "block";
      llmStdFieldsEl.style.display = "block";
      llmEqualLengthFieldsEl.style.display = "none";
      encodeBtn.textContent = "🤖 Encode with ONNX LLM";
      decodeBtn.textContent = "🔓 Decode with ONNX LLM";
    } else if (style === "equal-length") {
      llmPanelEl.style.display = "block";
      llmStdFieldsEl.style.display = "none";
      llmEqualLengthFieldsEl.style.display = "block";
      encodeBtn.textContent = "🤖 Encode with Equal-Length LLM";
      decodeBtn.textContent = "🔓 Decode with Equal-Length LLM";
    } else if (style === "poetry") {
      llmPanelEl.style.display = "none";
      encodeBtn.textContent = "🔒 Encode to Poetry";
      decodeBtn.textContent = "🔓 Decode to Plaintext";
    } else {
      llmPanelEl.style.display = "none";
      encodeBtn.textContent = "🔒 Encode to English Prose";
      decodeBtn.textContent = "🔓 Decode to Plaintext";
    }
  }

  styleEl.addEventListener("change", updateStyleUI);
  updateStyleUI();

  function showError(msg) {
    if (msg) {
      errorEl.textContent = msg;
      errorEl.style.display = "block";
    } else {
      errorEl.style.display = "none";
    }
  }

  function showStatus(msg, isSuccess) {
    if (msg) {
      statusEl.textContent = msg;
      statusEl.style.display = "block";
      if (isSuccess) {
        statusEl.style.backgroundColor = "rgba(34, 197, 94, 0.12)";
        statusEl.style.color = "#22c55e";
        statusEl.style.border = "1px solid rgba(34, 197, 94, 0.3)";
      } else {
        statusEl.style.backgroundColor = "rgba(59, 130, 246, 0.12)";
        statusEl.style.color = "var(--accent-primary)";
        statusEl.style.border = "1px solid rgba(59, 130, 246, 0.3)";
      }
    } else {
      statusEl.style.display = "none";
    }
  }

  function updateMetrics(text) {
    if (!text || !window.ngramCipher || !window.ngramCipher.analyzeCarrierText) {
      metricsEl.style.display = "none";
      return;
    }
    try {
      const a = window.ngramCipher.analyzeCarrierText(text);
      metricWords.textContent = a.wordCount;
      metricSentences.textContent = a.sentenceCount;
      metricAvgLen.textContent = a.avgSentenceLength.toFixed(1);
      metricVocabCov.textContent = (a.vocabularyCoverage * 100).toFixed(1) + "%";
      metricsEl.style.display = "flex";
    } catch {
      metricsEl.style.display = "none";
    }
  }

  copyBtn.addEventListener("click", async function() {
    const text = cipherEl.value;
    if (!text) return;
    try {
      await navigator.clipboard.writeText(text);
      const original = copyBtn.textContent;
      copyBtn.textContent = "✅ Copied!";
      setTimeout(() => copyBtn.textContent = original, 2000);
    } catch {
      cipherEl.select();
      document.execCommand("copy");
    }
  });

  async function ensureTransformersLoaded() {
    if (window.transformers && window.transformers.AutoTokenizer) {
      return window.transformers;
    }
    showStatus("⏳ Loading neural model engine (@huggingface/transformers)...", false);
    try {
      const module = await import("https://cdn.jsdelivr.net/npm/@huggingface/transformers@3.3.3");
      window.transformers = module;
      return module;
    } catch (err) {
      throw new Error("Failed to load @huggingface/transformers from CDN: " + (err.message || String(err)));
    }
  }

  function buildOptions() {
    const selectedStyle = styleEl.value;
    if (selectedStyle === "llm") {
      return {
        encoding: {
          style: "llm",
          llmModel: llmModelEl.value.trim() || "onnx-community/Supra-Mini-v2-0.1M-ONNX",
          llmPrompt: llmPromptEl.value.trim() || "In recent news,",
          bitsPerToken: parseInt(bitsPerTokenEl.value, 10) || 4
        }
      };
    }
    if (selectedStyle === "equal-length") {
      return {
        encoding: {
          style: "equal-length",
          llmModel: llmModelEl.value.trim() || "onnx-community/Supra-Mini-v2-0.1M-ONNX",
          equalLengthKeyPrompt: equalKeyPromptEl.value.trim() || "Here is an interesting observation:",
          equalLengthPlaintextPrompt: equalPlainPromptEl.value.trim() || "A text:"
        }
      };
    }
    return {
      encoding: {
        style: selectedStyle
      }
    };
  }

  encodeBtn.addEventListener("click", async function() {
    showError(null);
    try {
      const text = plainEl.value;
      const pass = passEl.value;
      if (!text) return showError("Please enter plaintext message to encode.");
      if (!pass) return showError("Please enter a password.");

      const isLlm = styleEl.value === "llm" || styleEl.value === "equal-length";
      if (isLlm) {
        await ensureTransformersLoaded();
        const rawModel = llmModelEl.value.trim() || "onnx-community/Supra-Mini-v2-0.1M-ONNX";
        const normalized = window.ngramCipher && window.ngramCipher.normalizeModelName
          ? window.ngramCipher.normalizeModelName(rawModel)
          : rawModel;
        showStatus('⏳ Downloading / loading ONNX model "' + normalized + '" from Hugging Face...', false);
      } else {
        showStatus(null);
      }

      const cipherLib = window.ngramCipher;
      if (!cipherLib || !cipherLib.encode) {
        throw new Error("Cipher engine library is not loaded.");
      }

      const result = await cipherLib.encode(text, pass, buildOptions());
      cipherEl.value = result;
      updateMetrics(result);
      showStatus(isLlm ? "✅ Encoding complete! ONNX model cached in browser IndexedDB." : "✅ Successfully encoded into natural carrier text!", true);
    } catch (err) {
      showStatus(null);
      showError(err.message || "Encoding error occurred.");
    }
  });

  decodeBtn.addEventListener("click", async function() {
    showError(null);
    try {
      const cipher = cipherEl.value;
      const pass = passEl.value;
      if (!cipher) return showError("Please enter carrier ciphertext to decode.");
      if (!pass) return showError("Please enter a password.");

      const isLlm = styleEl.value === "llm" || styleEl.value === "equal-length";
      if (isLlm) {
        await ensureTransformersLoaded();
        const rawModel = llmModelEl.value.trim() || "onnx-community/Supra-Mini-v2-0.1M-ONNX";
        const normalized = window.ngramCipher && window.ngramCipher.normalizeModelName
          ? window.ngramCipher.normalizeModelName(rawModel)
          : rawModel;
        showStatus('⏳ Loading ONNX model "' + normalized + '" for decoding...', false);
      } else {
        showStatus(null);
      }

      const cipherLib = window.ngramCipher;
      if (!cipherLib || !cipherLib.decode) {
        throw new Error("Cipher engine library is not loaded.");
      }

      const result = await cipherLib.decode(cipher, pass, buildOptions());
      plainEl.value = result;
      showStatus(isLlm ? "✅ Decoding complete!" : "✅ Successfully decoded and verified plaintext!", true);
    } catch (err) {
      showStatus(null);
      showError("Decryption failed: " + (err.message || "Incorrect password or corrupted carrier text."));
    }
  });
});
</script>

---

## 🔑 Key Architectural Features

1. **Robust Cryptography**:
   - Key derivation using **PBKDF2** with 100,000 SHA-256 iterations.
   - Symmetric authenticated encryption via **AES-256-GCM**.
   - Binary frame verification with CRC32 checksums and keystream whitening.
2. **Natural Carrier Prose (News & Poetry)**:
   - Dynamic grammatical sentence construction prevents structural repetition within subsequent sentences.
   - Context continuation probabilities prevent unnatural keyword clustering.
3. **100% Losslessly Reversible**:
   - Power-of-two slot allocation guarantees bit-exact extraction without precision drift.
4. **Adaptive Compression**:
   - Transparent pre-encryption payload compression with `gzip` or common-word dictionary packing.

---

## 📦 Installation & Usage

Install the package via npm:

```bash
npm install ngram-cipher
```

### Modern ESM / TypeScript

```typescript
import { encode, decode } from "ngram-cipher";

// 1. Encode into journalistic news prose
const carrier = await encode("Classified update at midnight", "StrongPassword123");
console.log(carrier);
/*
"The critical market expanded 15.0% in Paris. Johnson stated that the central bank
raised interest rates 5.1%, but the agency rejected the proposal..."
*/

// 2. Decode back to original secret text
const plaintext = await decode(carrier, "StrongPassword123");
console.log(plaintext); // "Classified update at midnight"
```

### Browser Script Tag

Include the global build directly from our site:

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
