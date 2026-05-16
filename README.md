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
- Supply Feed - automatically tracks market rates and undercuts or matches competitors
- Persistent trade history with profit tracking across restarts
- Sack of Gems auto-unpack - when a trade requires a partial gem amount, the bot automatically unpacks only the minimum number of sacks needed to cover the trade; no manual unpacking required
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

Automatically fetch market rates from other bots and adjust your own rates to stay competitive. Choose from six price modes:

| Mode | Description |
|---|---|
| **Off** | Manage rates manually |
| **Auto Cheap** | Undercut the cheapest bot by your offset |
| **Match Market** | Match the best rate exactly |
| **Average Market** | Sit at the market midpoint ± offset |
| **Buy Side Only** | Auto-adjust buy rates, sell stays manual |
| **Sell Side Only** | Auto-adjust sell rates, buy stays manual |
| **Auto Premium** | Sit above the market average by your offset |

The bot excludes its own listing from the market data so it never undercuts itself.

![Supply Feed](https://steamtradebots.com/assets/images/Bots/SteamGemBot/Supplyfeed.png)


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
