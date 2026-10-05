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


## Chat Bridge (Discord & Telegram)

Let your traders use the bot from **Discord** or **Telegram** instead of Steam chat. Trading still happens through normal Steam trade offers, only the conversation moves.

**Why you might want this.** Steam counts what your account *sends*. A bot that greets every new friend, answers every mistyped command and prints a long help list is producing a lot of outbound messages, and that is what gets an account flagged. The Chat Bridge gives traders a better place to talk, and quietens Steam chat right down.

**One Discord bot runs all of your bots.** These settings are app-wide, not per bot, so you only ever need a single token no matter how many bots you run.

### What traders can do without linking anything

`/rates` `/stock` `/owner` `/help`

These need no setup from the trader at all. Anyone in your server can see your rates.

### What needs a linked Steam account

`/check` `/sellcheck` `/quote` need to know which Steam account they are asking about. `/buy` and `/sell` need it **verified**, because otherwise someone could point the bot at a stranger and have it send trade offers to people who never asked for them.

Linking is one command and one Steam message, once, forever.

---

## Setting up Discord

### 1. Create the application

1. Go to <https://discord.com/developers/applications> and click **New Application**. Name it whatever you like, this is what traders will see.
2. Open the **Bot** tab, click **Reset Token**, and copy it. Treat it like a password.
3. **Check that "Interactions Endpoint URL" on the General Information page is empty.** If anything is in that box, Discord sends commands there instead of to your bot and nothing will work. This is the single most common setup problem.

> You do **not** need to enable any Privileged Gateway Intents. The bot uses slash commands, which need none of them.

### 2. Invite it to your server

Start the card bot with the token saved, then open the **Logs** page. The bot prints an invite link at startup:

```
[Bridge] Invite this bot with https://discord.com/api/oauth2/authorize?client_id=...
```

Open that link and pick your server. The permissions it asks for are View Channels, Send Messages, Manage Channels, Manage Messages, Embed Links and Read Message History. Manage Channels is what lets it create and tidy the per-bot channels below. Read Message History looks unnecessary, since the bot never reads conversations, but Discord requires it to pin a message and to check whether anyone has posted in a channel before retiring it.

> **If the Chat Bridge page says permissions are missing**, the bot was invited before it asked for all of them. A Discord bot keeps the permissions it was invited with, so open the invite link again and re-authorise. Discord updates the bot you already have rather than adding a second one. Until then channels still work, but the bot cannot pin a message in them or tidy them up.

### 3. Paste the token

**Chat Bridge** page → **Discord Bot Token** → tick **Accept commands on Discord** → **Save**, then **Stop and Start** the bot. The bridge only attaches when a fresh Steam session comes up.

### 4. Server ID (recommended)

In Discord, turn on **Settings → Advanced → Developer Mode**. Right-click your server name → **Copy Server ID**, and paste it into **Server ID**.

Without this, Discord can take up to an hour to publish your commands the first time. With it, they appear immediately. Worth setting even if you only use it while testing.

---

## Bot channels

Each of your bots gets its own channel, named after it, so traders always know which bot they are talking to. **The channel is the bot.**

```
CARD BOTS
  # low          talks to "Low"
  # high         talks to "High"
  # gem-trader   talks to "Gem Trader"
```

A command typed in `#low` goes to Low and nowhere else. No arguments, nothing to remember.

### Setting it up

1. In Discord, create an empty **category** (right-click in the channel list → Create Category). Call it whatever you like.
2. Right-click the **category heading** → **Copy Category ID**. This is a long number, not the name.
3. Paste it into **Bot Channels Category ID** on the Chat Bridge page and **Save**.
4. Click **Create / update bot channels**.

Every bot you have configured gets a channel, including when you only run one, so the category always reads as a complete list. Each channel gets a pinned line saying which bot it belongs to, and its topic shows live rates and stock.

### It keeps itself in order

| You do this | The bot does this |
|---|---|
| Rename a bot | Renames its channel to match |
| Add a bot | Creates a channel for it |
| Drag a channel out of the category | Moves it back |
| Delete a bot | Removes its now-dead channel |
| Click sync again | Nothing, it never makes duplicates |

### What the bot is allowed to change

Two switches on the Chat Bridge page, both on unless you turn them off.

| Switch | On | Off |
|---|---|---|
| **Remove channels for deleted bots** | A dead room is deleted | It is kept and marked as retired |
| **Rename channels when a bot is renamed** | The channel name follows the bot name | Your own channel names are left alone |

Renaming is the only thing a sync does to a name you may have chosen yourself, which is why it
can be switched off. A channel belongs to its bot by id, not by name, so renaming one by hand
never breaks the link and the bot keeps answering there. After a sync the page says how many
names it left alone, so an idle-looking result is never a silent failure.

**Deleting is careful.** A channel is only ever removed if this bot created it *and* nobody has typed in it. Slash replies are private, so a bot channel normally holds nothing but the pinned line. If a real person has posted there, it is kept and simply marked as retired. A retired channel also stops answering: a command typed in it gets a short note saying the bot that lived there was removed, rather than being quietly answered by whichever other bot happens to be running. You can switch removal off entirely with **Remove channels for deleted bots**.

> Traders can also message the bot directly instead of using a channel. With one bot running that just works. With several, the bot asks which one you meant and lists the channels.

---

## Setting up Telegram

Much shorter, no developer account needed:

1. Open Telegram and message **@BotFather**.
2. Send `/newbot` and follow the two prompts.
3. Copy the token it gives you into **Telegram Bot Token**, tick **Accept commands on Telegram**, **Save**, then Stop and Start the bot.

Traders open your bot in Telegram and type `/` to see every command. The bot's `t.me` link is worked out automatically, you do not need to enter it.

**Running more than one bot?** Discord gives each bot its own channel, which says who you are
talking to. Telegram has no channels, so the trader names the bot on the command itself:

    /rates bot:Low
    /check bot:Low

They do not have to memorise anything. `/botlist` lists every bot with what to type and which
are online, and `/help` repeats it at the bottom whenever more than one bot is running. The name
can go anywhere in the line and is never read as an argument. With a single bot it can be left
off entirely, so a one-bot owner never sees any of this.

A bot whose name contains a space, say "Gem Trader", is reached as `bot:gem-trader`, because the
command line is split on spaces. `/botlist` always shows the form that works.

---

## What changes on Steam

Once a bridge is running, Steam chat stops being a menu and becomes a signpost.

| | Bridge off | Bridge on |
|---|---|---|
| New friend | Full welcome message | Short greeting pointing at Discord or Telegram |
| `!HELP` | The full command list | One line pointing at Discord or Telegram |
| An unknown `!command` | "Unknown command" reply | Silence |
| Someone spamming | Three warnings, then unfriended | Silently timed out, then unfriended |
| Trading commands | All work | Handled on Discord or Telegram instead |

Every message is worded one of **15 different ways**, because sending identical text to everybody is exactly what looks automated. The bot also pauses and shows Steam's typing indicator rather than replying instantly.

**You are exempt.** Admin SteamIDs keep full command access on Steam, so you never lose control of your own bot.

**With no bridge configured, none of this applies.** The bot talks exactly as it always has.

### Telling traders where to go

Two options under **Telling traders where to go**:

- **Point at my profile** (default). The bot says *"the invite is on my Steam profile"* and never types a link. Steam scores accounts that send links, so this is the quieter choice. **Put your invite in your Steam profile summary first**, or traders hit a dead end.
- **Post the actual invite link**. Simpler for traders, at the cost of every message carrying a URL.

Either way, fill in **Server Invite Link** with the `https://discord.gg/...` invite you hand to traders. That field is what arms the whole quiet mode: with nowhere to send people, the bot stays talkative on Steam rather than pointing at nothing.

> The friend-list status line on the **Bot Settings** page now understands `{discord}` and `{telegram}` too, so you can advertise your invite there without the bot sending anything at all.

---

### Offering a Steam group invite

Off by default. Switch on **Offer a Steam group invite** and give it a group ID, and the signpost
gains one closing line:

> Nearly everything runs through Discord now, nicer for everybody trading. The invite is on my
> Steam profile whenever you fancy it.
>
> There is a link on my profile, and I can send you a Steam group invite if you say yes.

**The invite is sent only when that trader replies yes.** Not after a trade, not on a timer, and
never to anybody who has not asked. That last part matters: an invite nobody asked for is what
Steam treats as spam, and it is the bot account that gets reported for it. An earlier version of
this bot invited every trading partner automatically and that is exactly why it was removed.

What counts as yes is deliberately narrow: a short reply such as *yes*, *ok*, *sure*, *invite me*.
A sentence is not a yes, so "yes but only the good ones" gets nothing. A no gets silence rather
than another message. One invite per person, and a yes only counts for 15 minutes after the offer.

The offer line comes in 15 phrasings and the confirmation in another 15, so the pair never repeats.
Leave the switch off and the bot never mentions a group at all.

## How a trader links their Steam account

1. They add your bot on Steam as normal. **The bot only links accounts it is already friends with**, which is what stops it being used to message strangers.
2. They run `/link 7656...` with their SteamID64.
3. Your bot sends them **one** Steam message containing a 6-character code.
4. They reply `/verify ABC123`. That is the only Steam message they will ever get.
5. `/buy` and `/sell` now work, with **every** bot you run, not just the one they used.

### Trade URLs

A trader who also runs `/tradeurl <their Steam trade URL>` can be sent offers by **any** of your bots without adding each one as a friend. Worth suggesting if you run several.

The bot checks the trade URL actually belongs to the account they verified, so nobody can point your offers at somebody else. If they later regenerate their trade URL, the bot notices, forgets the old one, and tells them to run `/tradeurl` again.

---

## Chat Bridge troubleshooting

| What you see | What it means |
|---|---|
| *"That kind of interaction is not handled here"* | **Interactions Endpoint URL is set** in the Discord developer portal. Clear it. |
| *"This command is outdated"* | Discord is still publishing your commands. Set the **Server ID** for instant registration, and press Ctrl+R in Discord. |
| Commands do not appear at all | The bot was invited without the `applications.commands` scope. Re-invite using the link in your Logs. |
| Channels are not created | The bot is missing **Manage Channels** on that category, or the Category ID is a name rather than an id. |
| Duplicate channels | Give the bot **View Channels** on the category. It cannot see what it already made. |

The **Logs** page shows a line the moment any command arrives:

```
discord: interaction received: rates
```

If a trader reports a problem and that line is missing, Discord never reached the bot, so the cause is one of the first three rows above. If it is there, the log will say what happened next.

---

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

| Steam chat | Discord / Telegram | What it does | Needs |
|---|---|---|---|
| `!COMMANDS` / `!HELP` | `/help` | List everything I can do | anyone |
| `!PRICES` | `/rates` | My current buy and sell rates | anyone |
| `!STOCK` | `/stock` | How many gems and keys I have | anyone |
| `!OWNER` | `/owner` | My owner Steam profile | anyone |
| `!CHECK` | `/check` | What I could buy from you | SteamID |
| `!SELLCHECK` | `/sellcheck` | What I could sell you | SteamID |
| `!SUPPORT <msg>` | `/support <msg>` | Send a message to my owner | SteamID |
| `!CHECKTF <n>` | `/quote tf2 <n>` | What an amount would get you (no offer sent) (TF2 keys) | SteamID |
| `!CHECKTOD <n>` | `/quote tod <n>` | What an amount would get you (no offer sent) (ToD tickets) | SteamID |
| `!BUYTF <n>` | `/buy tf2 <n>` | Buy gems with keys, I send you a trade offer (TF2 keys) | linked |
| `!BUYTOD <n>` | `/buy tod <n>` | Buy gems with keys, I send you a trade offer (ToD tickets) | linked |
| `!SELLTF <n>` | `/sell tf2 <n>` | Sell me gems for keys, I send you a trade offer (TF2 keys) | linked |
| `!SELLTOD <n>` | `/sell tod <n>` | Sell me gems for keys, I send you a trade offer (ToD tickets) | linked |

**Needs:** `anyone` works with no identity at all. `SteamID` means the bot has to know which Steam
account you are, either because you linked one or because you passed it. `linked` means a verified
linked account, because the command sends a real trade offer and the bot will not aim one at an
unproven account.

The two spellings are the same command. With the Chat Bridge running the bot rewrites its own
replies as well, so a usage hint that reads `!BUYTF 5` on Steam reads `/buy tf2 5` on Discord. A trader is never shown a command they cannot type.


**On Telegram with more than one bot, name the one you want:** `/rates bot:Low`, `/check bot:Low`.
Discord does not need this, because the channel already says which bot you are talking to. Telegram
has no channels, so the name goes on the command. It can sit anywhere in the line and is never
treated as an argument. A bot called "Gem Trader" also answers to `bot:gem-trader`. With only one
bot running you can leave it off entirely.
**Discord and Telegram only.** These are about the bridge itself, so they have no Steam chat

`/botlist` on Telegram shows every bot, whether it is online, and exactly what to type for each.
It is a Telegram command only: on Discord the channel already tells you which bot you are talking
to, so there is nothing to list.
spelling. A trader runs them in the bot's channel or in a direct message.

| Command | What it does |
|---|---|
| `/link <steamid> [tradeurl]` | Link your Steam account so you can trade |
| `/verify <code>` | Finish linking with the code I sent you on Steam |
| `/unlink` | Forget the Steam account linked here |
| `/whoami` | Show which Steam account is linked here |
| `/tradeurl <tradeurl>` | Set your trade URL so any bot can send you offers |

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
