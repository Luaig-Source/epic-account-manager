# Epic Account Manager

A desktop tool for managing multiple Epic Games accounts for Rocket League — create temp email inboxes, store Epic tokens, fetch Psyonix stats, and launch the game directly.

---

## Download

Grab the latest **AccountManager.exe** from the [Releases](https://github.com/Luaig-Source/epic-account-manager/releases/latest) page. No installer needed — just run the exe.

---

## First-Time Setup

On first launch you will see a welcome screen with Terms of Use. Accept it, then configure the app in **Settings** (⚙️ button in the toolbar).

### 1 · FreeCustom API Key (recommended email provider)

FreeCustom gives you unlimited disposable inboxes with a real-time API.

1. Go to **[freecustom.email](https://freecustom.email)** and create a free account.
2. Open your **Dashboard → API** section.
3. Copy your **Bearer token** (starts with `Bearer eyJ…`).
4. In the app: **Settings → API Keys → FreeCustom API Key** → paste and click **Save**.

### 2 · Boomlify API Key (alternative email provider)

1. Go to **[boomlify.com](https://boomlify.com)** and sign up.
2. Open your **Dashboard** and copy the **API Key**.
3. In the app: **Settings → API Keys → Boomlify API Key** → paste and click **Save**.

> You only need **one** of the two above. FreeCustom is preferred.

### 3 · Rocket League Executable

Required to launch RL accounts directly from the app.

1. In the app: **Settings → Rocket League → Browse…**
2. Navigate to your RL install and select **RocketLeague.exe**.
   - Default path: `C:\Program Files\Epic Games\rocketleague\Binaries\Win64\RocketLeague.exe`
3. Click **Save**.

---

## Creating an Account

1. Click **+ New Account** (or `Ctrl+N`).
2. Choose an email provider tab:
   - **FreeCustom** — auto-generates an inbox using your API key.
   - **Boomlify** — creates a 1-day disposable address.
   - **Manual** — enter any email address manually.
3. Click **Generate Email** to create the inbox.
4. Click **↻ Roll** to generate a random Epic username and default password (or type your own).
5. Click **Save Account**.

The account is saved locally. You can then register it at [epicgames.com/register](https://www.epicgames.com/id/register/epic) using the generated email and password.

---

## Setting an Epic Token

An Epic token (`eg1~…`) is required to launch Rocket League or fetch Psyonix stats.

1. **Right-click** an account → **Set Epic Token** (or open **Edit → Account** tab → Epic Token field).
2. Click **Get Token** to open [legendary.gl/epiclogin](https://legendary.gl/epiclogin) in an incognito window.
3. Log in with the account's Epic credentials.
4. Copy the **authorization code** shown on the page.
5. Paste it into the token field and click **Apply** — the app converts it to a full token automatically.

Tokens refresh automatically every 45 minutes while the app is open.

---

## Fetching Stats

1. Select one or more accounts (or use the toolbar **↻ Fetch Stats** to fetch all visible accounts).
2. Stats fetched: 1v1 / 2v2 / 3v3 rank, XP level, in-game name, club, recent match history.
3. Stats appear in the table and in the **Edit → Stats** tab.

> Fetching stats briefly authenticates with the Psyonix backend and may disconnect an active Epic Launcher session for that account.

---

## Launching Rocket League

1. Right-click an account → **🚀 Launch Rocket League**.
2. The app exchanges the token for a one-time code and passes it to `RocketLeague.exe`.

---

## Features

| Feature | Description |
|---------|-------------|
| Temp email inbox | Create & read FreeCustom or Boomlify inboxes directly in the app |
| Auto token refresh | Silently refreshes Epic tokens every 45 min |
| Psyonix stats | Rank, level, IGN, club, match history |
| Direct RL launch | Launch RL with any stored token — no launcher needed |
| Virtual controllers | Map keyboard keys to Xbox controller buttons (requires ViGEm driver) |
| Status tracking | Active / Inactive / Banned / Pending labels |
| Search & filter | Full-text search + status filter |
| Auto-update | Checks GitHub Releases on startup and applies updates silently |
| Data nuke | Settings → Data → Delete All Data removes everything |

---

## Virtual Controller (optional)

Requires the **[ViGEm Bus Driver](https://github.com/nefarius/ViGEmBus/releases/latest)** to be installed. Without it, the 🎮 button is hidden.

Once installed, open the controller manager and assign keyboard keys to controller buttons for each virtual gamepad.

---

## Data & Privacy

All data is stored locally at:
```
%APPDATA%\RocketLeagueTools\AccountManager\
```

Nothing is sent anywhere except:
- Requests to the Psyonix / Epic API when you explicitly fetch stats or launch a game.
- Requests to FreeCustom / Boomlify when you generate or read an inbox.
- A version check against the GitHub Releases API on startup (anonymous, read-only).

---

## Auto-Update

The app checks [GitHub Releases](https://github.com/Luaig-Source/epic-account-manager/releases) on every launch. If a newer version is available, a dialog prompts you to update. The new exe is downloaded, verified, and relaunched automatically.

---

*by Luaig*
