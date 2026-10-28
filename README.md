# DEX Swapper AUTO

Monitoring a swap opportunity is only part of the work: the trader also needs to inspect the amount, fees, wallet readiness and what happened after an attempt. DEX Swapper AUTO brings those tasks into one trading dashboard and adds threshold-based automation for supported DNX sales. It helps keep the market comparison, manual controls and automatic trading preferences in the same workspace.

## Tech stack

| Layer | Technologies |
|---|---|
| Application | Python; FastAPI; Web3.py |
| Dashboard | JavaScript; HTML; CSS |
| Trading ecosystem | Ethereum; 1inch; Uniswap; MEXC market data |

## Read the opportunity before acting

The dashboard puts the supported swap quotes, exchange-price comparison, wallet balances and fee context together. Users can inspect the amounts they follow and compare the displayed spread without rebuilding the same view across several tools. A displayed spread is a screening observation; fees, liquidity and execution still affect the result.

Review the displayed opportunity and proposed trade conditions before choosing how to proceed. The comparison gives the operator a place to assess the current setup rather than treating an automatic signal as an instruction.

## Keep manual trading close at hand

Manual swap controls remain available alongside automatic mode. Trading preferences include the amount, slippage and gas settings, while the address book keeps frequently used addresses accessible. Connection indicators and balance refresh controls help establish whether the information needed for the next action is available.

Manual controls remain useful when a particular trade needs individual attention. They let the operator work from the same market context used to review the automatic strategy.

## Define the automatic DNX sale

Auto-Swap can trigger a supported DNX-to-USDC sale when the configured spread threshold is reached. Users can enable or disable automation, choose a cooldown and set a failure limit. Amount-related gas preferences support reviewing the intended trade sizes rather than relying on one fee preference for every amount.

Dry-run mode lets users inspect the automatic decision without sending a real swap. It is useful for checking the chosen threshold and observing when an attempt would be made. It does not establish that the same trade would be filled or profitable on a live market.

The automatic-sale settings express the operator's intended limits. Review the amount and conditions together so a saved configuration remains understandable when returning to the desk.

## Inspect quotes, allowances and submission choices

Quote-source selection gives users a choice among the supported pricing options, with feedback when an option is unavailable. The Approver view shows token allowances beside balances and supports allowance checks and explicit approvals. Approval actions are separate from simply viewing wallet information and can grant broad spending permission.

Supported builder selections expose enabled and connection states. The optional transaction watcher adds visibility into the watched activity. These controls provide operational context; they do not promise protection from every adverse trading condition.

Quote and allowance information belongs close to the decision to submit. Inspecting these details in the same session helps avoid switching between disconnected tools to understand the proposed action.

## Review attempts and their outcomes

The Swap History view and automatic-attempt history help users revisit trading activity and distinguish successful, failed, skipped or dry-run outcomes. Logs provide supporting feedback when an operation cannot proceed. This makes it easier to connect a dashboard action with its recorded result.

History turns an attempted action into something that can be reviewed later. Compare the recorded outcome with the intended conditions before deciding whether a setting needs adjustment.

## Make the dashboard fit the session

Appearance and display preferences cover fonts, panel dimensions, spacing, visible information and the Auto-Swap banner. Users can adjust the workspace around the information they need and reset the presentation when required. This AUTO edition extends the separate manual-focused DEX Swapper product with its own automation controls.

Preferences and diagnostics support longer sessions as well as quick checks. Keep the current task readable and return to the recorded details when an attempt needs explanation.


---

Private implementation: [dex-swapper-auto](https://github.com/logicencoder/dex-swapper-auto)

Related product: [DEX Swapper](https://github.com/logicencoder/dex-swapper-overview). See [REPOS.md](REPOS.md) for repository links.

**[Logic Encoder](https://logicencoder.com)** · [GitHub](https://github.com/logicencoder) · [Contact](https://logicencoder.com/contact/)
