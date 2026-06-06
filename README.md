# A7sb — حسب
**Algerian Currency Converter**

A clean, single-file currency converter built for the Algerian market. Converts between 30+ world currencies with real-time rates, and includes a dedicated **Square Port Said parallel market (Black Market)** DZD estimator alongside the official rate.

---

[

![Open App](https://img.shields.io/badge/Open%20App-A7sb-c8973a?style=for-the-badge)

](https://kayo-isle69.github.io/A7sb/)

---

## Features

- **Live rates** via [Frankfurter API](https://frankfurter.dev) (free, no API key required)
- **Seed/cached rates** as fallback — works fully offline
- **Parallel market DZD estimate** using a manually tracked USD/DZD baseline (Square Port Said)
- Cross-rate formula display — shows exactly how the DZD amount was calculated
- 30+ currencies supported with flags and priority ordering
- Responsive, mobile-friendly UI
- Zero dependencies — pure HTML, CSS, and vanilla JS

---

## Usage

No build step, no install. Just open the file:

```bash
open a7sb.html
```

Or host it anywhere — it's a single `.html` file.

---

## How the Parallel Market Rate Works

The app uses a manually maintained USD/DZD baseline (`ALGERIAN_BM_USD`) reflecting Square Port Said market rates. For non-USD currencies, it cross-converts through USD first:

```
Amount ÷ (Currency/USD rate) = USD value
USD value × BM_USD_rate = DZD estimate
```

> ⚠️ The parallel market rate is a manual reference and does not reflect an official or regulated exchange rate. Update `ALGERIAN_BM_USD` in the source as needed.

---

## Updating Rates

**Live rates** refresh automatically on load via Frankfurter. For the parallel market baseline, edit this line in the script:

```js
const ALGERIAN_BM_USD = 248; // Update manually
```

**Seed rates** (used when offline) can also be updated in `SEED_RATES` with fresh values from any public forex source.

---

## Stack

- HTML / CSS / Vanilla JavaScript
- [Frankfurter API](https://frankfurter.dev) — free, open-source exchange rate API
- [Syne](https://fonts.google.com/specimen/Syne) + [DM Mono](https://fonts.google.com/specimen/DM+Mono) — Google Fonts

---

## License

MIT — do whatever you want with it.
