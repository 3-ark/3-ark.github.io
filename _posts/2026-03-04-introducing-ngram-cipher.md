---
layout: post
title: "Introducing N-Gram Cipher: Reversible Natural English Steganography"
date: 2026-03-04 12:00:00 +0000
categories: [cryptography, release, steganography]
tags: [cryptography, aes-gcm, n-gram, typescript, steganography, open-source]
---

We are excited to introduce [**`3-ark/ngram-cipher`**](https://github.com/3-ark/ngram-cipher)—a modern cryptographic steganography engine for JavaScript and TypeScript!

`ngram-cipher` transforms encrypted payloads into natural-sounding, syntactically coherent English prose (journalistic reports) or poetic verses that are **100% losslessly reversible**.

---

## Why N-Gram Steganography?

Traditional steganography conceals data in image pixels, audio waveforms, or whitespace formatting. However, when communicating across text-only messaging channels, email, or social media platforms, non-text files are often heavily re-encoded, stripped, or flagged by security scanners.

`ngram-cipher` solves this by transforming ciphertext directly into realistic natural language text:
* **AES-256-GCM Authenticated Encryption**: Strong symmetric security with PBKDF2 key derivation (100,000 SHA-256 iterations).
* **Statistical Language Models**: Uses dynamic N-gram statistical scoring from Google Books datasets to ensure word continuations follow natural syntactic and semantic distributions.
* **Grammar & Variety Rules**: Generates varied sentence structures with appositives, clauses, and reporting verbs, while actively preventing structural repetition across consecutive sentences.
* **100% Exact Recovery**: Employs power-of-two slot allocation and CRC32 verification to ensure bit-exact decryption every time.

---

## Interactive Browser Demo

You can try the cipher directly in your browser on our new documentation page:

👉 **[Try the N-Gram Cipher Interactive Demo]({{ '/docs/ngram-cipher/' | relative_url }})**

```typescript
import { encode, decode } from "ngram-cipher";

// Encrypt & hide in news prose
const carrierText = await encode("Top secret deployment instructions", "ArkPassword123");
console.log(carrierText);
/*
"A regional leader approved the measure. The executive announced the directive in Paris;
Local investment remained 14.5% in Madrid..."
*/

// Reversibly extract & decrypt
const decrypted = await decode(carrierText, "ArkPassword123");
console.log(decrypted); // "Top secret deployment instructions"
```

Check out the code and documentation on [GitHub](https://github.com/3-ark/ngram-cipher).
