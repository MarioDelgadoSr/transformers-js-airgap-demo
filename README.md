# transformers-js-airgap-demo
Interactive demonstration of 100% in-browser, air-gapped sentiment analysis using Transformers.js, WebAssembly, and local CacheStorage inspection.
# ✈️ In-Browser Sentiment Analysis (100% Client-Side Air-Gap Demo)

An interactive demonstration showing how to run transformer-based natural language processing models directly inside the web browser using **Transformers.js** (v3), **WebAssembly (WASM)**, and **ONNX Runtime Web**. 

Once the initial model payload is loaded, execution transitions to a **100% offline, air-gapped state** where no text or network requests leave the user's local device.

🔗 **Live Interactive Demo:** [ObservableHQ Notebook](https://observablehq.com/@mariodelgadosr/hello-hugging-face)

---

## 📐 Air-Gap Architecture Model
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 720 300" width="100%" height="100%" style="background:#0f172a; font-family: system-ui, -apple-system, sans-serif;">
  <defs>
    <style>
      .label { fill: #f8fafc; font-size: 13px; font-weight: 600; }
      .subtext { fill: #94a3b8; font-size: 11px; }
      .accent { fill: #38bdf8; font-size: 12px; font-weight: 600; }
      .badge { fill: #22c55e; font-size: 11px; font-weight: 700; }
    </style>
    <!-- Severed Line Pattern -->
    <marker id="dot" viewBox="0 0 10 10" refX="5" refY="5" markerWidth="6" markerHeight="6">
      <circle cx="5" cy="5" r="3" fill="#ef4444"/>
    </marker>
  </defs>

  <!-- Title & Status -->
  <text x="30" y="35" class="label" font-size="16" fill="#f1f5f9">Client-Side Transformers.js Air-Gap Execution Model</text>
  <rect x="520" y="18" width="170" height="26" rx="13" fill="#166534" opacity="0.4"/>
  <rect x="520" y="18" width="170" height="26" rx="13" stroke="#22c55e" stroke-width="1" fill="none"/>
  <circle cx="535" cy="31" r="4" fill="#22c55e"/>
  <text x="548" y="35" class="badge">100% OFFLINE CAPABLE</text>

  <!-- Remote Server Box (Hugging Face) -->
  <g transform="translate(30, 75)">
    <rect width="180" height="180" rx="12" fill="#1e293b" stroke="#334155" stroke-width="1.5"/>
    <text x="20" y="35" class="label">Hugging Face Hub</text>
    <text x="20" y="55" class="subtext">CDN / Model Registry</text>

    <!-- ONNX Weights Icon -->
    <rect x="20" y="80" width="140" height="40" rx="6" fill="#0f172a" stroke="#475569" stroke-dasharray="3 3"/>
    <text x="30" y="105" class="subtext" fill="#cbd5e1">ONNX Model Weights</text>

    <text x="20" y="145" class="subtext" fill="#64748b">Initial Load Only ↓</text>
  </g>

  <!-- Connection / Severed Air Gap Area -->
  <g transform="translate(210, 75)">
    <!-- Active Fetch (Grayed/Crossed) -->
    <line x1="10" y1="90" x2="110" y2="90" stroke="#ef4444" stroke-width="2" stroke-dasharray="6 4"/>

    <!-- Air Gap Cut Marker -->
    <circle cx="60" cy="90" r="16" fill="#450a0a" stroke="#ef4444" stroke-width="1.5"/>
    <path d="M52 82 L68 98 M68 82 L52 98" stroke="#ef4444" stroke-width="2" stroke-linecap="round"/>

    <text x="60" y="130" text-anchor="middle" class="accent" fill="#f87171">AIR GAP</text>
    <text x="60" y="146" text-anchor="middle" class="subtext" fill="#94a3b8">Network Cut</text>
  </g>

  <!-- Local Browser Environment Box -->
  <g transform="translate(330, 75)">
    <rect width="360" height="180" rx="12" fill="#0f2942" stroke="#0284c7" stroke-width="2"/>
    <text x="20" y="35" class="label">Client Browser Sandbox</text>
    <text x="20" y="53" class="subtext">Local Execution (WebAssembly / ONNX Runtime)</text>

    <!-- Cache Layer -->
    <rect x="20" y="70" width="150" height="85" rx="8" fill="#1e293b" stroke="#38bdf8" stroke-dasharray="2 2"/>
    <text x="32" y="93" class="label" font-size="12">Browser Cache</text>
    <text x="32" y="110" class="subtext">IndexedDB / Cache API</text>
    <text x="32" y="138" class="accent">✓ Weights Stored</text>

    <!-- Arrow -->
    <path d="M170 112 L190 112" stroke="#38bdf8" stroke-width="2" marker-end="url(#dot)"/>

    <!-- Pipeline Engine -->
    <rect x="190" y="70" width="150" height="85" rx="8" fill="#0369a1" opacity="0.3"/>
    <rect x="190" y="70" width="150" height="85" rx="8" stroke="#38bdf8" stroke-width="1.5" fill="none"/>
    <text x="202" y="93" class="label" font-size="12">pipeline('sentiment')</text>
    <text x="202" y="112" class="subtext">Zero External API Calls</text>
    <text x="202" y="138" class="badge">Local Inference</text>
  </g>
</svg>
