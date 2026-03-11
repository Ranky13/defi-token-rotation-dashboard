# DeFi Token Rotation Dashboard  
**UNI · AAVE · LINK · LDO · SNX**  
*(All ERC-20 tokens on Ethereum mainnet)*

A Power BI dashboard visualizing daily on-chain transfer flows and capital rotation patterns for five foundational Ethereum DeFi tokens:

- **UNI** – Uniswap (leading DEX & liquidity provision)  
- **AAVE** – Aave (top lending & borrowing protocol)  
- **LINK** – Chainlink (decentralized oracle infrastructure)  
- **LDO** – Lido (dominant liquid staking for ETH)  
- **SNX** – Synthetix (synthetic assets & perpetuals platform)

These tokens were selected because they represent **core infrastructure** rather than short-term speculative assets. They have high TVL, meaningful utility, strong governance, and consistent on-chain activity — making them ideal for tracking macro DeFi rotation signals (internal liquidity vs. external exits vs. large-player movements).

![Dashboard Overview](/img/snapshot.PNG)  


## What the Dashboard Tracks

- Daily transfer volume in USD  
- Directional flows: internal DeFi (DEX/traders), external (CEX/Binance users), whale/large transfers, unlabeled/retail wallets  
- Rotation intensity (activity × churn proxy)  
- Percentage composition of flows over time  

The goal is to spot macro shifts: capital staying in DeFi, exiting to centralized exchanges, or being repositioned by whales/smart money.

## Key Charts Explained

All four charts with the KPI Cards are fully interactive:  
- The **Token slicer** at the top filters **all charts simultaneously** to show data for only the selected token (or "All" for combined view).  
- The **Date range slicer** lets you zoom into any period within the available data (~last 60 days).  
- Hover over any chart for exact $ amounts, percentages, and dates.

### 1. KPI Cards (Quick Summary)
- **What they show**: Instant highlights of the latest or key metrics:  
  - Latest Sum of total volume in USD ($)
  - Current % to DEX/traders  
  - Current % to CEX/Binance users  
  - Largest large transfer (> $100k) in view  
  - Whale (> $1m ) % transfer

- **Purpose**: Provides at-a-glance insight without digging into charts.  
- **How to read**: Values update dynamically with slicers (token/date range). Formatted as percentage (%).
![Dashboard Overview](/img/snapshot.PNG)  


### 2. Daily Volume Trend (100% Stacked Column Chart)
- **What it shows**: Daily total transfer volume in USD, broken down by flow category (stacked columns).  
  When a single token is selected via the slicer, the chart displays these five categories for that token only:
  - **DEX / Trader Flow** (blue/green) — internal DeFi & trader activity
  - **CEX / Binance Flow** (red/orange) — movement to Binance-related addresses
  - **Large Transfers > $100k** (purple/yellow) — big single transfers (whale proxy)
  - **Unlabeled Flow** (gray) — normal/retail wallets
  - **Whale Flow** (> $1M transfers) — very large moves (high-signal)
- **Purpose**: Shows the **composition** of daily volume for the selected token and highlights rotation direction (e.g. rising red = more exit pressure).  
- **How to read**: Each colored segment = that category’s share of the day’s total. Total height varies (not forced to 100%). Hover shows $ value per category.
![Daily Volume Trend](/img/daily%20token%20flow.PNG)  


### 3. % Flow Composition Over Time (Stacked Area Chart)
- **What it shows**: Percentage breakdown of flows over time (areas fill to 100% each day).  
  When a token is selected via the slicer, it shows the same five categories for that token:
  - **DEX / Trader Flow**
  - **CEX / Binance Flow**
  - **Large Transfers > $100k**
  - **Unlabeled Flow**
  - **Whale Flow** (> $1M)
- **Purpose**: Makes it easy to see shifts in relative importance (e.g. CEX area growing = increasing exit rotation).  
- **How to read**: Each colored area = % share of daily volume (always sums to 100%). Hover shows exact % and USD value per category and date.
![% Flow Composition Over Time](/img/%25%20flow%20comparison.PNG)  


### 4. Rotation Intensity Proxy (Line Chart)
- **What it shows**: Daily rotation intensity score (active addresses × transfer frequency proxy) for each token.  
  The Token slicer filters this chart to show one line (selected token) or multiple lines (All).  
- **Purpose**: Flags periods of high churn/turnover — useful for spotting momentum, whale activity, or sudden interest.  
- **How to read**: Higher line = higher rotation activity. Hover for exact score value.
![Rotation Intensity](/img/rotation.PNG)  


### 5. Total Volume USD (Area Chart)
- **What it shows**: Total daily transfer volume in USD (filled area under the line).  
  The Token slicer updates this chart (and all others) to show volume for only the selected token — or combined when "All" is chosen.  
- **Purpose**: Provides a smooth, visual overview of overall activity level and trends for the selected token(s).  
- **How to read**: Higher/filled area = higher total volume that day. Hover shows exact $ amount.
![Total Volume USD](/img/sum.PNG)  


All charts refresh from live Dune data and respond instantly to slicer changes.



## How to Use

1. Download the `.pbix` file  
2. Open in **Power BI Desktop**   
3. Click **Refresh** (connects to live Dune API data)  
4. Use **Token** slicer to focus on one or compare all  
5. Use **Date range** slicer to zoom into periods  
6. Hover over charts for detailed $ and % values  
7. Click elements to cross-filter (e.g. click a token legend → all visuals update)

## Data Source & Methodology

- **Blockchain**: Ethereum mainnet only (all tokens are ERC-20)  
- **Source**: Dune Analytics (`tokens.transfers` table + `labels.addresses` + price feeds)  
- **Timeframe**: ~last 60 days (auto-updates on refresh)  
- **USD conversion**: Dune-integrated prices (CoinGecko + others)  
- **Large/whale proxy**: Threshold-based (> $100k and > $1M single transfers)  
- **Original Dune query**: [https://dune.com/ranky13/defi-money-movement-dashboards]


This project showcases:

- **On-chain data proficiency** — Dune SQL (transfer filtering, label joins, USD normalization)  
- **DeFi domain knowledge** — understanding of Ethereum infrastructure tokens and capital flow dynamics  
- **Data visualization & BI** — Power BI (DAX measures, dynamic formatting, slicers, scheduled refresh)  
- **End-to-end workflow** — query design → data modeling → interactive dashboard → storytelling  
- **Focus on signal over noise** — choosing long-term DeFi primitives instead of speculative assets


## License

MIT License — free to use, modify, share. Attribution appreciated.

## Author

**ranky**  
Lagos, Nigeria  
March 2026

Built to explore and visualize real DeFi capital rotation on Ethereum.

