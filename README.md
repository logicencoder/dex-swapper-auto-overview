# DEX Swapper AUTO

Selling a token when the DEX price is above the exchange price takes quotes, fees, wallet readiness and fast execution at once. DEX Swapper AUTO is a self-hosted trading dashboard that compares DEX quotes for configured amounts of DNX with the MEXC price about ten times a second, lets the operator swap by hand, and can start a DNX-to-USDC sale automatically when the price gap passes a threshold. Swaps are sent to MEV builders first, and every attempt, real or dry-run, is recorded.

## Tech stack

| Layer | Technologies |
|---|---|
| Application | Python with FastAPI, Web3.py and a WebSocket feed to the dashboard |
| Quotes and routing | 1inch router and API, Uniswap V3 and direct pool quotes, an RPC router |
| Market data | MEXC price feed |
| Submission | MEV builders (Titan, Beaver, Flashbots) with the public mempool as fallback |
| History | SQLite swap history with profit and loss |
| Dashboard | JavaScript, HTML and CSS |

## The arbitrage table

The dashboard's central table lists the configured amounts. For each, it shows the DEX sell price, the MEXC price and the profit in percent, refreshed about every 100 milliseconds. It sits next to wallet balances, gas settings and connection indicators, so the operator reads the opportunity and the readiness to act on one screen.

## Manual swaps

An amount is picked from the table, a quote is fetched and the swap is confirmed by the operator. The Trading settings hold amount, slippage and gas preferences, the Addresses tab keeps a book of frequently used addresses, and a quote-source choice selects automatic, unoswap2, direct pool, the 1inch API or Uniswap V3, with feedback when a source is unavailable.

## Auto-Swap

When enabled, Auto-Swap looks at the table and picks the row with the largest dollar profit among rows above the threshold, which defaults to 10 percent. It waits at least 12 seconds between swaps and stops after three failures in a row. Before sending, it re-quotes with fresh prices and skips the attempt when the gap has disappeared, and those skips are recorded as stale. A dry-run mode makes the same decisions and records what it would have done without sending anything, and Auto-Swap is off by default. The last 50 attempts are kept with their status: success, failed, error, skipped as stale or dry run.

## Approver and submission

The Approver tab lists token allowances beside balances, checks an allowance and sends an explicit approval, which is a separate action from viewing the wallet. Titan, Beaver and Flashbots builders can be switched on and off, with Titan, Beaver and Flashbots enabled by default and their connection state shown. A nonce coordinator keeps transactions in order, and a block monitor watches a submitted transaction.

## History and preferences

Swap History records each swap with its outcome and computes profit and loss from a SQLite store. Appearance and Display tabs set fonts, panel dimensions, spacing, visible information and the Auto-Swap banner, and a reset restores the defaults. This AUTO edition extends the manual DEX Swapper with the automation controls.

---

Private implementation: [dex-swapper-auto](https://github.com/logicencoder/dex-swapper-auto)

Related product: [DEX Swapper](https://github.com/logicencoder/dex-swapper-overview). See [REPOS.md](REPOS.md) for repository links.

**[Logic Encoder](https://logicencoder.com)** · [GitHub](https://github.com/logicencoder) · [Contact](https://logicencoder.com/contact/)
