/* =========================================================
   Nova65 Cloud Landing — index.js (FULL REPLACEMENT)
   =========================================================
   What this adds/implements (all in one file):
   ✅ Dollar (USD) pricing section (Build / Govern / Operate)
   ✅ “One subscription” positioning (access + usage + assurance)
   ✅ Smooth-scroll to Pricing
   ✅ Buttons wired (Open Admin / Build an App / Go to Pricing)
   ✅ Pricing toggles (Monthly / Annual) with -20% annual discount
   ✅ Feature comparison + FAQ
   ✅ No secrets, safe for Cloudflare Pages
   ========================================================= */

(() => {
  "use strict";

  /* ================================
     CONFIG — update these if needed
     ================================ */
  const CONFIG = {
    brand: "Nova65 Cloud",
    adminUrl: "https://nova65.com/admindashboard",
    buildUrl: "https://nova65.com", // your main builder landing
    apiBase: "https://cloud.nova65.com",
    contactEmail: "support@nova65.com", // change if you prefer
    annualDiscountPct: 20
  };

  /* ================================
     PRICING (USD)
     ================================ */
  const PRICING = {
    currencySymbol: "$",
    billingCadence: "monthly", // default UI state: "monthly" | "annual"
    tiers: [
      {
        id: "build",
        name: "Build",
        tagline: "Conversion-first membership",
        priceMonthly: 29,
        included: [
          "URL → APK/AAB + iOS ZIP builds",
          "Build history + rebuilds",
          "Basic app overview",
          "Key issuance (API key) for your app"
        ],
        highlights: [
          "Great for agencies & MVPs",
          "Fastest path to shipped apps"
        ],
        features: {
          builds: "Included quota + overage",
          governance: "Present (logging only)",
          intent: "Basic logging",
          identity: "Basic keys",
          billing: "Tracking only",
          support: "Standard"
        },
        cta: { label: "Start with Build", href: CONFIG.buildUrl }
      },
      {
        id: "govern",
        name: "Govern",
        badge: "Most Popular",
        tagline: "Assurance + visibility unlocked",
        priceMonthly: 99,
        included: [
          "Everything in Build",
          "Governance visibility (Trust status, warnings)",
          "Usage metering dashboards",
          "Key lifecycle tooling (rotate, revoke)",
          "Billing status + exports"
        ],
        highlights: [
          "Perfect for SaaS teams",
          "Turn governance into product trust"
        ],
        features: {
          builds: "Higher quota + overage",
          governance: "Visible + enforced limits",
          intent: "Summaries + exports",
          identity: "Key lifecycle + roles",
          billing: "Billing status + exports",
          support: "Priority"
        },
        cta: { label: "Upgrade to Govern", href: `${CONFIG.adminUrl}` }
      },
      {
        id: "operate",
        name: "Operate",
        tagline: "Enterprise-grade control plane",
        priceMonthly: 499,
        included: [
          "Everything in Govern",
          "Advanced enforcement (policy modes)",
          "Audit log browsing (Intent Ledger)",
          "Custom plans + customer records",
          "Readiness for regulated environments"
        ],
        highlights: [
          "Institutions & compliance-led orgs",
          "SLA-ready foundation"
        ],
        features: {
          builds: "Enterprise quota + negotiated",
          governance: "Full enforcement + policy controls",
          intent: "Audit browsing + advanced analytics",
          identity: "Institution controls (roadmap-ready)",
          billing: "Ops-grade exports + integrations",
          support: "Dedicated"
        },
        cta: { label: "Talk to Sales", href: `mailto:${CONFIG.contactEmail}?subject=Nova65%20Operate%20Plan%20-%20Request` }
      }
    ]
  };

  /* ================================
     DOM helpers
     ================================ */
  const $ = (sel, root = document) => root.querySelector(sel);
  const $$ = (sel, root = document) => Array.from(root.querySelectorAll(sel));

  function safeText(el, text) {
    if (!el) return;
    el.textContent = String(text ?? "");
  }

  function setAttr(el, name, value) {
    if (!el) return;
    el.setAttribute(name, String(value));
  }

  function fmtUsd(amount) {
    // keep it simple and deterministic for marketing pages
    return `${PRICING.currencySymbol}${Number(amount).toFixed(0)}`;
  }

  function discountedAnnual(monthly, discountPct) {
    // annual price displayed as "per month billed annually" using a discount
    const discounted = monthly * (1 - discountPct / 100);
    return Math.max(0, Math.round(discounted));
  }

  function scrollToId(id) {
    const el = document.getElementById(id);
    if (!el) return;
    el.scrollIntoView({ behavior: "smooth", block: "start" });
  }

  /* ================================
     Render pricing section
     ================================ */
  function renderPricing() {
    const wrap = $("#pricing");
    if (!wrap) return;

    // If your HTML already contains pricing markup, we’ll replace the inside of #pricing
    wrap.innerHTML = `
      <div class="section-head">
        <h2>Pricing (Worldwide — USD)</h2>
        <p class="muted">
          One Nova65 subscription. Governance is always present, and you unlock more assurance as you grow.
        </p>

        <div class="billing-toggle" role="group" aria-label="Billing cadence">
          <button class="toggle-btn is-active" data-cadence="monthly">Monthly</button>
          <button class="toggle-btn" data-cadence="annual">Annual <span class="pill">-${CONFIG.annualDiscountPct}%</span></button>
        </div>
      </div>

      <div class="pricing-grid" id="pricingGrid"></div>

      <div class="compare">
        <h3>What changes as you upgrade</h3>
        <div class="compare-grid" id="compareGrid"></div>
      </div>

      <div class="faq">
        <h3>FAQ</h3>
        <div class="faq-grid" id="faqGrid"></div>
      </div>
    `;

    const cadenceBtns = $$(".toggle-btn", wrap);
    cadenceBtns.forEach((btn) => {
      btn.addEventListener("click", () => {
        cadenceBtns.forEach((b) => b.classList.remove("is-active"));
        btn.classList.add("is-active");
        PRICING.billingCadence = btn.dataset.cadence === "annual" ? "annual" : "monthly";
        paintPricingCards();
        paintCompare();
      });
    });

    paintPricingCards();
    paintCompare();
    paintFaq();
  }

  function paintPricingCards() {
    const grid = $("#pricingGrid");
    if (!grid) return;

    grid.innerHTML = PRICING.tiers
      .map((t) => {
        const isAnnual = PRICING.billingCadence === "annual";
        const price = isAnnual
          ? discountedAnnual(t.priceMonthly, CONFIG.annualDiscountPct)
          : t.priceMonthly;

        const priceLabel = isAnnual
          ? `${fmtUsd(price)} <span class="per">/mo</span> <span class="billed">(billed annually)</span>`
          : `${fmtUsd(price)} <span class="per">/mo</span>`;

        const badge = t.badge ? `<div class="badge">${escapeHtml(t.badge)}</div>` : "";

        return `
          <div class="pricing-card ${t.id === "govern" ? "is-featured" : ""}">
            ${badge}
            <h4>${escapeHtml(t.name)}</h4>
            <p class="tagline">${escapeHtml(t.tagline)}</p>
            <div class="price">${priceLabel}</div>

            <ul class="included">
              ${t.included.map((x) => `<li>${escapeHtml(x)}</li>`).join("")}
            </ul>

            <div class="highlights">
              ${t.highlights.map((x) => `<span class="chip">✓ ${escapeHtml(x)}</span>`).join("")}
            </div>

            <a class="cta-btn" href="${escapeAttr(t.cta.href)}" target="_blank" rel="noopener">
              ${escapeHtml(t.cta.label)}
            </a>

            <div class="fineprint">
              Builds may include quota + fair-use. Governance enforcement and audit visibility increase by tier.
            </div>
          </div>
        `;
      })
      .join("");
  }

  function paintCompare() {
    const grid = $("#compareGrid");
    if (!grid) return;

    const isAnnual = PRICING.billingCadence === "annual";

    const cols = PRICING.tiers.map((t) => {
      const price = isAnnual ? discountedAnnual(t.priceMonthly, CONFIG.annualDiscountPct) : t.priceMonthly;
      return {
        id: t.id,
        name: t.name,
        priceText: isAnnual ? `${fmtUsd(price)}/mo (annual)` : `${fmtUsd(price)}/mo`,
        f: t.features
      };
    });

    const rows = [
      { key: "builds", label: "Builds (URL → APK/AAB/iOS)" },
      { key: "governance", label: "Governance (Trust Constitution)" },
      { key: "intent", label: "Intent Ledger (auditability)" },
      { key: "identity", label: "Identity (keys, lifecycle, roles)" },
      { key: "billing", label: "Billing (status/exports)" },
      { key: "support", label: "Support" }
    ];

    grid.innerHTML = `
      <div class="compare-table">
        <div class="compare-row compare-head">
          <div class="cell feature">Feature</div>
          ${cols
            .map(
              (c) => `
              <div class="cell tier">
                <div class="tier-name">${escapeHtml(c.name)}</div>
                <div class="tier-price">${escapeHtml(c.priceText)}</div>
              </div>`
            )
            .join("")}
        </div>

        ${rows
          .map((r) => {
            return `
              <div class="compare-row">
                <div class="cell feature">${escapeHtml(r.label)}</div>
                ${cols
                  .map((c) => `<div class="cell tier">${escapeHtml(String(c.f[r.key] ?? ""))}</div>`)
                  .join("")}
              </div>
            `;
          })
          .join("")}
      </div>
    `;
  }

  function paintFaq() {
    const grid = $("#faqGrid");
    if (!grid) return;

    const faq = [
      {
        q: "Is this only for Nova65 apps?",
        a: "Nova65 Cloud is designed for Nova65 builds, but the control-plane pattern (keys, usage, governance) is API-first and can expand."
      },
      {
        q: "Do I pay twice (conversion + governance)?",
        a: "No. The subscription gives access; builds are quota/usage; governance tiers unlock higher assurance and enforcement."
      },
      {
        q: "Can I stay conversion-only?",
        a: "Yes. Stay on Build tier. Governance is present (logging) but not enforced until you upgrade."
      },
      {
        q: "How do I start as a company (tenant)?",
        a: "You start by converting your app (or onboarding an existing build), receiving keys, then using the console to monitor usage and upgrade assurance when needed."
      },
      {
        q: "Where are payments handled?",
        a: "Your landing page can link to Stripe checkout/portal. The Cloud Edge worker already supports billing status and exports; Stripe integration can be phased in safely."
      }
    ];

    grid.innerHTML = faq
      .map(
        (x) => `
        <details class="faq-item">
          <summary>${escapeHtml(x.q)}</summary>
          <p class="muted">${escapeHtml(x.a)}</p>
        </details>
      `
      )
      .join("");
  }

  /* ================================
     Header buttons + CTA wiring
     ================================ */
  function wireCtas() {
    // These selectors match common landing patterns. If your HTML differs, this still won’t break anything.
    const btnAdmin = $("[data-cta='open-admin']");
    const btnBuild = $("[data-cta='build-app']");
    const btnPricing = $("[data-cta='go-pricing']");
    const btnHeroPricing = $("[data-cta='hero-pricing']");

    if (btnAdmin) btnAdmin.addEventListener("click", () => window.open(CONFIG.adminUrl, "_blank", "noopener"));
    if (btnBuild) btnBuild.addEventListener("click", () => window.open(CONFIG.buildUrl, "_blank", "noopener"));

    if (btnPricing) btnPricing.addEventListener("click", () => scrollToId("pricing"));
    if (btnHeroPricing) btnHeroPricing.addEventListener("click", () => scrollToId("pricing"));

    // Optional: if you have a “Quickstart endpoints” panel, populate it
    const qs = $("#quickstartEndpoints");
    if (qs) {
      qs.innerHTML = `
        <div class="qs-row"><span class="mono">Admin identity</span><a class="mono" href="${CONFIG.apiBase}/admin/whoami" target="_blank" rel="noopener">/admin/whoami</a></div>
        <div class="qs-row"><span class="mono">Keys list</span><a class="mono" href="${CONFIG.apiBase}/admin/keys/list" target="_blank" rel="noopener">/admin/keys/list</a></div>
        <div class="qs-row"><span class="mono">Create key</span><a class="mono" href="${CONFIG.apiBase}/admin/keys/create" target="_blank" rel="noopener">/admin/keys/create</a></div>
        <div class="qs-row"><span class="mono">Client billing</span><a class="mono" href="${CONFIG.apiBase}/billing/status" target="_blank" rel="noopener">/billing/status</a></div>
      `;
    }

    // Optional: “Need access?” mailto
    const needAccess = $("[data-cta='need-access']");
    if (needAccess) {
      const subj = encodeURIComponent("Nova65 Cloud — Provision tenant access");
      const body = encodeURIComponent(
        "Hi Nova65 Cloud team,\n\nWe want to onboard as a tenant.\nCompany:\nWebsite:\nPrimary contact:\nUse case:\nExpected builds/month:\nGovernance tier (Build/Govern/Operate):\n\nThanks."
      );
      needAccess.setAttribute("href", `mailto:${CONFIG.contactEmail}?subject=${subj}&body=${body}`);
    }
  }

  /* ================================
     Minimal escaping helpers
     ================================ */
  function escapeHtml(str) {
    return String(str ?? "")
      .replaceAll("&", "&amp;")
      .replaceAll("<", "&lt;")
      .replaceAll(">", "&gt;")
      .replaceAll('"', "&quot;")
      .replaceAll("'", "&#039;");
  }
  function escapeAttr(str) {
    // extra safe for href attributes
    return escapeHtml(str).replaceAll("`", "&#096;");
  }

  /* ================================
     Ensure required containers exist
     (If your HTML doesn’t have #pricing, this will create one at the bottom)
     ================================ */
  function ensurePricingMount() {
    if ($("#pricing")) return;
    const main = $("main") || document.body;

    const sec = document.createElement("section");
    sec.id = "pricing";
    sec.className = "section section-pricing";
    main.appendChild(sec);
  }

  /* ================================
     Boot
     ================================ */
  function boot() {
    // Update brand text if placeholders exist
    safeText($("[data-brand='name']"), CONFIG.brand);

    // Make sure pricing exists, then render it
    ensurePricingMount();
    renderPricing();
    wireCtas();
  }

  if (document.readyState === "loading") {
    document.addEventListener("DOMContentLoaded", boot);
  } else {
    boot();
  }
})();
