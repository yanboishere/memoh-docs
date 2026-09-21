# Feishu (Lark) Channel Configuration

Memoh supports integrating with Feishu (Lark) via the Open Platform. This allows your enterprise bots to interact with users in groups or private chats.

## Step 1: Create a Feishu App

1. Go to the [Feishu Open Platform](https://open.feishu.cn/app) and log in.
2. Click **Create Custom App**.
3. Enter a name and description, then click **Create**.
4. In the left sidebar, go to **App Settings** > **Credentials & Basic Info**.
5. Copy your **App ID** and **App Secret**.

## Step 2: Enable Bot Capability

1. In the Feishu Developer Console, go to **Capabilities** > **Bot**.
2. Click **Enable Bot**.

## Step 3: Configure Permissions

1. Go to **Capabilities** > **Permissions**.
2. Search for and enable the following permissions (at minimum):
   - `im:message` (Receive and send messages)
   - `im:chat` (Access group chat information)
3. Click **Apply for Permissions** if required by your organization.

## Step 4: Connect It in Memoh (Default: Long Connection)

1. In Memoh, go to your Bot's **Platforms** tab and add a **Feishu** channel.
2. Keep **Inbound Mode** at its default: `websocket`.
3. Fill in your **App ID** and **App Secret**; if you use international Lark, switch **Region** to `lark`.
4. Click **Save**. Messages arrive over Feishu's **WebSocket long connection** — no public callback URL and no event-subscription setup needed.

## Step 5: Alternative — Webhook Mode

Choose this only when your server is publicly reachable and you prefer event callbacks:

1. Set **Inbound Mode** to `webhook`; besides the **App ID** and **App Secret**, also fill in the **Encrypt Key** and **Verification Token** matching your Event Subscriptions settings in the Feishu Console.
2. Click **Save**. Memoh will generate a **Webhook Callback URL** — copy it.
3. In the Feishu Console, go to **App Settings** > **Event Subscriptions**, paste the URL into the **Verification URL** field, and save.
4. Add events like `Receive Message` (im.message.receive_v1).

> Official Guide: [Feishu Custom Bot Guide](https://open.feishu.cn/document/client-docs/bot-v3/add-custom-bot)

## Step 6: Publish Your App

1. In the Feishu Console, go to **App Release** > **Version Management & Release**.
2. Click **Create a Version**, fill in the details, and submit for approval.
3. Once approved and published, the bot is ready to use.
