# Steam Gem Bot
[![Latest Release](https://img.shields.io/github/v/release/stardrix/steam-gem-bot-releases?label=Latest%20Release&style=for-the-badge&color=ff69b4)](https://github.com/stardrix/steam-gem-bot-releases/releases/latest)

Automated Steam trading bot for buying and selling **Steam Gems** in exchange for **TF2 Keys** and **Tour of Duty Tickets**. Whether you are flipping currencies or fueling the economy of your **Steam card bot for a level up profile**, this bot handles your gem supply automatically. Fully integrated with the #1 verified **Steam bot listing** directory.

## 🌐 The SteamTradeBots Ecosystem

To get the most out of your bot and build trust with your users, take advantage of our full ecosystem:

*   **📈 Get Traffic (Bot Directory):** Don't just run a bot get customers! Submit your account to our official **[Steam Bot Listing](https://www.steamtradebots.com/)** to display your live stock and rates to thousands of users.
*   **🛡️ Build Trust (Chrome Extension):** Tell your customers to install the **[SteamTradeBots Verified Extension](https://chromewebstore.google.com/detail/steamtradebots-verified-b/ifbjmpaibhdfjemngaajlmijgopcaopk)**. It places a green "Verified Bot" banner directly on your bot's Steam profile, proving your legitimacy and protecting your users from impersonation scams.

## Features

- Run **multiple bot accounts** from a single dashboard - each with its own credentials, rates, and config
- Auto-accepts trade offers based on your configured rates - no manual input needed
- Live dashboard with inventory, trade history, rates, and logs
- Chat commands so users can check prices and request trades directly on Steam
- SteamTradeBots.com listing integration - your bot stays listed and up to date automatically
- Supply Feed - place your rates on the market ladder (undercut, low, mid, high, overcut) and let the bot keep them there automatically, inside a safety net of hard limits, a step limiter, feed sanity checks and a spread guard; per-currency follow, and your own bots never undercut each other
- Steam browser version keeps itself current - Steam rejects trade confirmations from bots that claim an outdated browser version; the bot checks the current Chrome version daily and tells you when a restart will apply a newer one
- Persistent trade history with profit tracking across restarts
- Sack of Gems auto-unpack - when a trade requires a partial gem amount, the bot automatically unpacks only the minimum number of sacks needed to cover the trade; no manual unpacking required
- Steam rate-limit resilience - smart inventory caching, spaced retries, serialized mobile confirmations with shared backoff, and a minimal background traffic profile keep trades flowing even when Steam throttles busy IPs (VPS-friendly)
- Optional SteamApis.com inventory mode - bypass Steam's per-IP rate limits entirely (free tier available); ideal for VPS/datacenter hosting
- Safe with concurrent buyers - items in unaccepted outgoing offers are reserved, so two users trading at the same moment always receive different items; when reserved stock is the bottleneck, the second buyer is politely asked to retry
- One active trade per user - a user with an open offer who orders again gets their existing offer link back instead of a duplicate offer (admins are exempt)
- Custom friend-list status - design the bot's "Now Playing" text with live placeholders like `{gems} gems - {buy_tf2}/{sell_tf2}`; stock and rates update in real time
- One-click Support Report - a button in the Logs tab bundles version, OS, bot state, and recent logs (secrets always redacted) into a single report for fast support; errors carry short reference codes with plain-language explanations
- Session self-heal and crash safety nets - expired Steam web sessions renew automatically, and unexpected errors are logged and shown instead of taking the app down silently
- Auto-updates - new versions install silently in the background


## How it works

1. Install and activate your license
2. Add one or more Steam bot account credentials
3. Set your buy and sell rates
4. Start the bot - it handles everything from there


## Dashboard

Live overview of the bot's status, inventory, uptime, and recent trades at a glance.

![Dashboard](https://steamtradebots.com/assets/images/Bots/SteamGemBot/Dashboard.png)


## Multi-Bot Support

Run multiple Steam accounts from one dashboard. Each bot has its own credentials, rates, listing config, and trade history - completely isolated from the others.

- Add or remove bots at any time from the **Bot Account** page
- Switch between bots using the dropdown in the sidebar
- The **Bot Overview** page shows all bots at a glance with live status, uptime, and trade counts
- Start or stop individual bots - or use **Start All** / **Stop All** for everything at once


## Bot Overview

Monitor all configured bots from a single grid view. Each card shows live status, uptime, and trade count. Start or stop any bot directly from here without switching accounts.


## Bot Account

Configure your Steam credentials, Web API Key, Shared Secret, Identity Secret, and admin settings. All sensitive fields are hidden behind a reveal toggle.

This page also holds the **Inventory Method** setting: leave it on **Steam** (default, free), or switch to **SteamApis** with an API key from [steamapis.com](https://steamapis.com) if your bot runs on a VPS whose IP Steam rate-limits heavily — inventory loading then bypasses Steam's limits entirely. Their free tier (500 requests/month) covers a typical small bot. Restart the bot after changing this setting.

The **Friend-list Status Text** field lets you design what the bot shows as its "game" in friend lists, built from live values: `{gems}` `{keys_tf2}` `{keys_tod}` and the rates `{buy_tf2}` `{sell_tf2}` `{buy_tod}` `{sell_tod}` — e.g. `{gems} gems - {buy_tf2}/{sell_tf2} (!Help)`. It updates automatically as stock and rates change; leave it empty for the default.

> **VPS tip:** Steam rate-limits by IP, and budget hosting ranges shared with many other bots often arrive pre-throttled. We recommend a premium VPS provider with a clean, dedicated IP. Quick test on any new VPS: open `https://steamcommunity.com/inventory/<your-bot-steamid64>/753/6` in a browser — a JSON response means the IP is fine; an immediate error on the first request means the range is throttled.

![Bot Account](https://steamtradebots.com/assets/images/Bots/SteamGemBot/Botacc.png)


## Rates

Set how many gems the bot gives or requires per TF2 Key and Tour of Duty Ticket. Changes apply instantly - no restart needed.

| Direction | Meaning |
|---|---|
| **Buy (gems/key)** | Gems the bot gives the user per key |
| **Sell (gems/key)** | Gems the user must pay per key |

![Rates](https://steamtradebots.com/assets/images/Bots/SteamGemBot/Rates.png)


## STB Listing

Connect your API Key to the #1 verified **Steam bot listing** at SteamTradeBots.com. Keep your listing live and up to date with your current rates and stock automatically, and instantly sync with the STB Chrome Extension for verified profile banners.

![STB Listing](https://steamtradebots.com/assets/images/Bots/SteamGemBot/STBlisting.png)

## Supply Feed

Fetches live rates from the other gem bots listed on SteamTradeBots.com and places your rates where you want them on the market. Apply by hand, or let the bot keep you there automatically, inside a safety net.

### Price Mode - a position on the market ladder

The market is tiered: cheap rates and premium rates sit side by side. Rather than a formula, you pick where to sit:

| Position | Where your rates land |
|---|---|
| **Off** | Manage rates by hand |
| **Undercut the cheapest bot** | Cheaper than everyone, by your offset |
| **Low** | Among the cheapest bots |
| **Mid-Low** | Between the cheap end and the middle |
| **Mid** | The middle of the market |
| **Mid-High** | Between the middle and the expensive end |
| **High** | Among the most expensive bots |
| **Overcut the most expensive bot** | Dearer than everyone, by your offset |

Your price side is placed at that point in the market, and the other side is set at the spread the bots around that point actually run. No position can ever cross (give more than you take back).

- **Adjust**: move both sides, only what you give, or only what you take.
- **Follow the market for**: tick the currencies the feed may touch (TF2 and ToD). Unticked currencies keep the rates you set by hand.
- **Offsets**: one per currency, used only by the two "cut" positions.

### Automatic updates

A per-bot switch, **off by default**. Switched on, the bot re-fetches the market on your interval while it is running and applies the suggestion itself, with the dashboard open or closed. Fetch Now and Apply keep working as before.

### The safety net

Every automatic run passes through these, so a market spike or a competitor's typo can never empty your bot:

| Net | What it does | Your control |
|---|---|---|
| **Hard limits** | Per currency: the most you will ever give and the least you will ever take | See *Hard limits* below |
| **Max change per update** | One run moves a rate at most this much | 1 to 50%, default 10; cannot be switched off |
| **Minimum bots to trust a rate** | A "market" of one bot is where typos live | 1 to 10, default 2 |
| **Ignore extreme rates** | Quotes far above or below the market median are dropped | On or off, default on |
| **Spread guard** | The bot will never give more per key than it takes back; a trader could loop that until you are empty | Always on, not a setting |

Anything the safety net stops is held, not applied: the rate stays where it was and the Supply page says why. Every run is logged.

### Hard limits

A wall automatic updates never cross, per currency and per side: the most the bot will ever give, and the least it will ever take. **There is always a wall from day one.** Every bot ships with these defaults, chosen from the live market so they sit outside it by a margin (bots today give about 3200 to 3400 gems per TF2 key and take 3500 to 3800): they never touch a bot that is pricing normally, and they stop a runaway in either direction, including a crowd of bots on Undercut ratcheting each other down.

| Currency | Max the bot gives | Min the bot takes |
|---|---|---|
| TF2 | 5000 gems per key | 2500 gems per key |
| ToD | 2000 gems per ticket | 1000 gems per ticket |

On the Supply page each box comes filled in with its default. You can:

- **Move a wall**: type your own number. It saves on its own; the **Save limits** button confirms it with a timestamp if you want to be sure.
- **Remove a wall**: clear the box. The moment you start editing, a yellow notice explains what clearing does. Once a box is blank it turns red, and a red notice names every side that now has no wall, because nothing then stops a runaway there. Put a number back in and it clears.

A side you never touched keeps its default, so an owner who never opens the page is still protected. A side you cleared stays cleared across restarts; that is your choice, and the red notice stays until you change it. The same walls apply when you click Apply by hand.

**All of your own bots are excluded from the market**, running or stopped, so your bots never undercut each other.

**Fetch Now is a true preview.** It shows each suggestion with its verdict (applied, capped at your limit, or held), plus what the next automatic run would change. If the feed cannot be fetched, the message tells you what happened and what to do; a rejected key means your Supplier subscription on steamtradebots.com needs checking.

![Supply Feed](https://steamtradebots.com/assets/images/Bots/SteamGemBot/Supplyfe1ed.png)

## Trade History

Persistent trade log that survives restarts. Filter by **Today**, **7 Days**, or **30 Days**. Summary cards show:

- Accepted and declined trade counts
- Net gems received vs sent
- Net TF2 Keys and Tour of Duty Tickets

![Trade History](https://steamtradebots.com/assets/images/Bots/SteamGemBot/TradeHistory.png)


## Deposit

Displays the bot's trade URL so you can send items to the bot directly from another account.

![Deposit](https://steamtradebots.com/assets/images/Bots/SteamGemBot/Deposit.png)


## Withdraw

Send gems, TF2 Keys, or Tour of Duty Tickets from the bot to any Steam account. Admin only.

![Withdraw](https://steamtradebots.com/assets/images/Bots/SteamGemBot/Withdraw.png)


## Chat Monitor

Live feed of all Steam chat messages and support requests the bot receives. Commands are logged with the user's Steam ID and response.

![Chat Monitor](https://steamtradebots.com/assets/images/Bots/SteamGemBot/ChatMonitor.png)


## Maintenance

Manage the bot's friend list automatically. Configure:

- Auto-accept friend requests
- Auto-reject group invites
- Auto-cleanup old friends who haven't traded recently
- Maximum friend list size

![Maintenance](https://steamtradebots.com/assets/images/Bots/SteamGemBot/Maintenance.png)


## Logs

Raw bot log output. Shows INFO, WARN, and ERROR entries. Supports one-click clear.

The **🛟 Support Report** button gathers everything support needs — app version, OS, bot state, and the recent log — into one report, copied to your clipboard and saved as a file. Passwords, secrets, and API keys are never included. If something goes wrong, send that one paste instead of screenshots.

![Logs](https://steamtradebots.com/assets/images/Bots/SteamGemBot/Logs.png)


## Chat Commands

Users can interact with the bot directly over Steam chat:

| Command | Description |
|---|---|
| `!HELP` / `!COMMANDS` | List all available commands |
| `!PRICES` | Show current buy and sell rates |
| `!STOCK` | Show bot's current inventory |
| `!OWNER` | Show the owner's Steam profile link |
| `!SUPPORT <msg>` | Send a support message to the owner |
| `!CHECK` | Show your gem, TF2 Key, and ToD inventory |
| `!SELLCHECK` | Show how many gems your keys/tickets are worth |
| `!CHECKTF <n>` | Check the gem value of n TF2 Keys |
| `!CHECKTOD <n>` | Check the gem value of n ToD Tickets |
| `!BUYTF <n>` | Trade n TF2 Keys → receive gems |
| `!BUYTOD <n>` | Trade n ToD Tickets → receive gems |
| `!SELLTF <n>` | Trade gems → receive n TF2 Keys |
| `!SELLTOD <n>` | Trade gems → receive n ToD Tickets |

> User inventory must be set to **Public** for any command that involves a trade.


## Getting a license

Visit **[steamtradebots.com](https://www.steamtradebots.com/)** to get access to the bot. You can purchase your license directly from the dashboard on our website.

Not sure if you want to run a bot forever?
Try out our 6-month plan or get a lifetime license!

## Requirements

- Windows 10/11 (x64)
- Linux (x64)
- A Steam account dedicated to being the bot
- Steam Web API Key ([get one here](https://steamcommunity.com/dev/apikey))
- Shared Secret and Identity Secret from your Steam authenticator (SteamDesktopAuthenticator or WinAuth)
- A valid Steam Card Bot license

---


## Support & community

Have questions or need help? Join the Discord:

**[discord.gg/XCtgnPsZFU](https://discord.gg/XCtgnPsZFU)**


*This repository contains release builds only. New versions are pushed here automatically and installed silently by the app.*
