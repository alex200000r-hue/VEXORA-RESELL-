[index.html](https://github.com/user-attachments/files/35214646/index.html)
<!DOCTYPE html>
<html lang="ro">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>VEXORA RESELL</title>
  <style>
    :root {
      --bg-main: #0c0e12;
      --bg-card: #181b20;
      --bg-card-hover: #1f232a;
      --border-subtle: #262b33;
      --text-primary: #e6e9ef;
      --text-secondary: #8e95a2;
      --accent-blue: #3b82f6;
      --accent-green: #22c55e;
      --accent-red: #f43f5e;
      --btn-grad-start: #2563eb;
      --btn-grad-end: #3b82f6;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
      -webkit-tap-highlight-color: transparent;
    }

    body {
      background-color: var(--bg-main);
      color: var(--text-primary);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      padding: 0 18px 40px 18px;
    }

    .app-container {
      width: 100%;
      max-width: 440px;
      display: flex;
      flex-direction: column;
    }

    header {
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 28px 0 24px 0;
    }

    .back-btn {
      position: absolute;
      left: 0;
      top: 50%;
      transform: translateY(-25%);
      background: transparent;
      border: none;
      color: var(--text-secondary);
      cursor: pointer;
      padding: 8px;
      display: none;
      align-items: center;
      justify-content: center;
      transition: color 0.15s ease, transform 0.15s ease;
    }

    .back-btn.visible {
      display: flex;
    }

    .back-btn:hover {
      color: var(--text-primary);
    }

    .back-btn:active {
      transform: translateY(-25%) scale(0.92);
    }

    .brand-title {
      font-size: 18px;
      font-weight: 700;
      letter-spacing: 2.2px;
      text-transform: uppercase;
      color: #d8dde6;
    }

    .view {
      display: none;
      flex-direction: column;
      gap: 18px;
      animation: fadeIn 0.18s ease-out;
    }

    .view.active {
      display: flex;
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translateY(4px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    .menu-card {
      background-color: var(--bg-card);
      border: 1px solid var(--border-subtle);
      border-radius: 16px;
      padding: 28px 20px;
      text-align: center;
      cursor: pointer;
      transition: background-color 0.15s ease, transform 0.12s ease, border-color 0.15s ease;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 8px;
    }

    .menu-card:hover {
      background-color: var(--bg-card-hover);
      border-color: #343b46;
    }

    .menu-card:active {
      transform: scale(0.985);
    }

    .menu-card-title {
      font-size: 20px;
      font-weight: 700;
      letter-spacing: 0.2px;
    }

    .title-paysafe {
      color: var(--accent-blue);
    }

    .title-vbucks {
      color: var(--accent-green);
    }

    .title-robux {
      color: var(--accent-red);
    }

    .menu-card-sub {
      font-size: 14px;
      color: var(--text-secondary);
      font-weight: 400;
    }

    .gen-header {
      text-align: center;
      margin-top: 8px;
      margin-bottom: 6px;
    }

    .gen-title {
      font-size: 22px;
      font-weight: 700;
      margin-bottom: 6px;
    }

    .gen-format {
      font-size: 14px;
      color: var(--text-secondary);
      font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
      letter-spacing: 0.3px;
    }

    .slider-card {
      background-color: var(--bg-card);
      border: 1px solid var(--border-subtle);
      border-radius: 16px;
      padding: 20px 20px 22px 20px;
    }

    .slider-top {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 18px;
    }

    .slider-label {
      font-size: 16px;
      color: #c5cbd6;
      font-weight: 500;
    }

    .slider-value {
      font-size: 18px;
      font-weight: 700;
      color: var(--text-primary);
      font-variant-numeric: tabular-nums;
    }

    input[type="range"] {
      -webkit-appearance: none;
      appearance: none;
      width: 100%;
      height: 6px;
      border-radius: 999px;
      background: linear-gradient(
        to right,
        #ffffff 0%,
        #ffffff var(--progress, 0%),
        #323741 var(--progress, 0%),
        #323741 100%
      );
      outline: none;
      cursor: pointer;
    }

    input[type="range"]::-webkit-slider-thumb {
      -webkit-appearance: none;
      appearance: none;
      width: 22px;
      height: 22px;
      border-radius: 50%;
      background: #ffffff;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.5);
      cursor: pointer;
      transition: transform 0.1s ease;
    }

    input[type="range"]::-webkit-slider-thumb:hover {
      transform: scale(1.06);
    }

    input[type="range"]::-moz-range-thumb {
      width: 22px;
      height: 22px;
      border: none;
      border-radius: 50%;
      background: #ffffff;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.5);
      cursor: pointer;
    }

    .generate-btn {
      width: 100%;
      padding: 17px 20px;
      border: none;
      border-radius: 14px;
      background: linear-gradient(90deg, var(--btn-grad-start) 0%, var(--btn-grad-end) 100%);
      color: #ffffff;
      font-size: 16px;
      font-weight: 700;
      letter-spacing: 1.2px;
      text-transform: uppercase;
      cursor: pointer;
      box-shadow: 0 6px 20px rgba(37, 99, 235, 0.28);
      transition: filter 0.15s ease, transform 0.12s ease;
    }

    .generate-btn:hover {
      filter: brightness(1.07);
    }

    .generate-btn:active {
      transform: scale(0.985);
    }

    .results-section {
      display: flex;
      flex-direction: column;
      gap: 12px;
      margin-top: 6px;
    }

    .results-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .results-label {
      font-size: 15px;
      color: #b5bcc8;
      font-weight: 500;
    }

    .copy-btn {
      background-color: var(--bg-card);
      border: 1px solid #303641;
      color: #d6dce6;
      font-size: 13px;
      font-weight: 500;
      padding: 8px 16px;
      border-radius: 10px;
      cursor: pointer;
      transition: background-color 0.15s ease, border-color 0.15s ease, color 0.15s ease;
    }

    .copy-btn:hover {
      background-color: var(--bg-card-hover);
      border-color: #434b59;
    }

    .copy-btn.copied {
      border-color: var(--accent-green);
      color: var(--accent-green);
    }

    .results-box {
      background-color: var(--bg-card);
      border: 1px solid var(--border-subtle);
      border-radius: 16px;
      padding: 18px;
      min-height: 240px;
      max-height: 360px;
      overflow-y: auto;
      font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, monospace;
      font-size: 14px;
      line-height: 1.65;
      color: var(--text-secondary);
      white-space: pre-wrap;
      word-break: break-all;
      user-select: text;
    }

    .results-box.has-codes {
      color: var(--text-primary);
    }
  </style>
</head>
<body>
  <div class="app-container">
    <header>
      <button id="backBtn" class="back-btn" type="button" aria-label="Înapoi">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
          <path d="M15.5 5.5L7.5 12l8 6.5v-13z" />
        </svg>
      </button>
      <div class="brand-title">VEXORA RESELL</div>
    </header>

    <main id="menuView" class="view active">
      <div class="menu-card" data-type="paysafe">
        <div class="menu-card-title title-paysafe">Generează Paysafe</div>
        <div class="menu-card-sub">16 cifre numerice (Încep cu 0)</div>
      </div>

      <div class="menu-card" data-type="vbucks">
        <div class="menu-card-title title-vbucks">Generează V-Bucks</div>
        <div class="menu-card-sub">16 caractere (Alfanumeric majuscule)</div>
      </div>

      <div class="menu-card" data-type="robux">
        <div class="menu-card-title title-robux">Generează Robux</div>
        <div class="menu-card-sub">16 caractere (Alfanumeric majuscule)</div>
      </div>
    </main>

    <section id="generatorView" class="view">
      <div class="gen-header">
        <h1 id="genTitle" class="gen-title title-paysafe">Generator Paysafe</h1>
        <div id="genFormat" class="gen-format">Format: 0XXXXXXXXXXXXXXX</div>
      </div>

      <div class="slider-card">
        <div class="slider-top">
          <label for="quantitySlider" class="slider-label">Cantitate coduri:</label>
          <span id="quantityValue" class="slider-value">1</span>
        </div>
        <input id="quantitySlider" type="range" min="1" max="50" value="1" />
      </div>

      <button id="generateBtn" class="generate-btn" type="button">GENEREAZĂ</button>

      <div class="results-section">
        <div class="results-header">
          <span class="results-label">Rezultate:</span>
          <button id="copyAllBtn" class="copy-btn" type="button">Copiază tot</button>
        </div>
        <div id="resultsBox" class="results-box">Codurile vor apărea aici...</div>
      </div>
    </section>
  </div>

  <script>
    const CONFIGS = {
      paysafe: {
        title: "Generator Paysafe",
        titleClass: "title-paysafe",
        format: "Format: 0XXXXXXXXXXXXXXX",
        generate: () => {
          let code = "0";
          for (let i = 0; i < 15; i++) {
            code += Math.floor(Math.random() * 10);
          }
          return code;
        }
      },
      vbucks: {
        title: "Generator V-Bucks",
        titleClass: "title-vbucks",
        format: "Format: XXXXXXXXXXXXXXXX",
        generate: () => {
          const chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
          let code = "";
          for (let i = 0; i < 16; i++) {
            code += chars.charAt(Math.floor(Math.random() * chars.length));
          }
          return code;
        }
      },
      robux: {
        title: "Generator Robux",
        titleClass: "title-robux",
        format: "Format: XXXXXXXXXXXXXXXX",
        generate: () => {
          const chars = "ABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789";
          let code = "";
          for (let i = 0; i < 16; i++) {
            code += chars.charAt(Math.floor(Math.random() * chars.length));
          }
          return code;
        }
      }
    };

    const menuView = document.getElementById("menuView");
    const generatorView = document.getElementById("generatorView");
    const backBtn = document.getElementById("backBtn");
    const genTitle = document.getElementById("genTitle");
    const genFormat = document.getElementById("genFormat");
    const quantitySlider = document.getElementById("quantitySlider");
    const quantityValue = document.getElementById("quantityValue");
    const generateBtn = document.getElementById("generateBtn");
    const copyAllBtn = document.getElementById("copyAllBtn");
    const resultsBox = document.getElementById("resultsBox");

    let currentType = "paysafe";
    const PLACEHOLDER_TEXT = "Codurile vor apărea aici...";

    function updateSliderVisual() {
      const min = Number(quantitySlider.min);
      const max = Number(quantitySlider.max);
      const val = Number(quantitySlider.value);
      const percent = ((val - min) / (max - min)) * 100;
      quantitySlider.style.setProperty("--progress", `${percent}%`);
      quantityValue.textContent = val;
    }

    function openGenerator(type) {
      currentType = type;
      const cfg = CONFIGS[type];

      genTitle.textContent = cfg.title;
      genTitle.className = `gen-title ${cfg.titleClass}`;
      genFormat.textContent = cfg.format;

      quantitySlider.value = 1;
      updateSliderVisual();

      resultsBox.textContent = PLACEHOLDER_TEXT;
      resultsBox.classList.remove("has-codes");
      copyAllBtn.textContent = "Copiază tot";
      copyAllBtn.classList.remove("copied");

      menuView.classList.remove("active");
      generatorView.classList.add("active");
      backBtn.classList.add("visible");
    }

    function openMenu() {
      generatorView.classList.remove("active");
      menuView.classList.add("active");
      backBtn.classList.remove("visible");
    }

    function generateCodes() {
      const count = Number(quantitySlider.value);
      const cfg = CONFIGS[currentType];
      const list = [];

      for (let i = 0; i < count; i++) {
        list.push(cfg.generate());
      }

      resultsBox.textContent = list.join("\n");
      resultsBox.classList.add("has-codes");
      copyAllBtn.textContent = "Copiază tot";
      copyAllBtn.classList.remove("copied");
    }

    async function copyAllCodes() {
      if (!resultsBox.classList.contains("has-codes")) return;
      const text = resultsBox.textContent;

      try {
        await navigator.clipboard.writeText(text);
      } catch {
        const textarea = document.createElement("textarea");
        textarea.value = text;
        textarea.style.position = "fixed";
        textarea.style.opacity = "0";
        document.body.appendChild(textarea);
        textarea.select();
        document.execCommand("copy");
        document.body.removeChild(textarea);
      }

      copyAllBtn.textContent = "Copiat!";
      copyAllBtn.classList.add("copied");
      setTimeout(() => {
        copyAllBtn.textContent = "Copiază tot";
        copyAllBtn.classList.remove("copied");
      }, 1500);
    }

    document.querySelectorAll(".menu-card").forEach((card) => {
      card.addEventListener("click", () => {
        openGenerator(card.dataset.type);
      });
    });

    backBtn.addEventListener("click", openMenu);
    quantitySlider.addEventListener("input", updateSliderVisual);
    generateBtn.addEventListener("click", generateCodes);
    copyAllBtn.addEventListener("click", copyAllCodes);

    updateSliderVisual();
  </script>
</body>
</html>
