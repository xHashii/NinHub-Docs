# Inviting NinHub Bot & Permissions

To get started with NinHub, you'll first need to invite the bot to your Discord server.

## Invite Link

Use the official invite link below:

**[➡️ Add NinHub to Your Server](https://discord.com/oauth2/authorize?client_id=YOUR_BOT_CLIENT_ID&permissions=YOUR_PERMISSIONS_INTEGER&scope=bot%20applications.commands)** 
*(Replace with your actual bot invite link, ensuring the client_id and permissions integer are correct)*

## Recommended Permissions

When you invite the bot, Discord will show you a list of permissions it's requesting. For full functionality, NinHub typically requires permissions such as:

*   **View Channels**
*   **Send Messages**
*   **Embed Links**
*   **Attach Files** (for some embeds or future features)
*   **Read Message History** (for command processing and context)
*   **Use External Emojis**
*   **Add Reactions** (for confirmations, etc.)
*   **Manage Channels** (for creating/deleting matchmaking voice channels)
*   **Move Members** (for moving players into matchmaking voice channels)
*   **Manage Webhooks** (for marketplace notifications)

The permissions integer in the invite link should cover these. If you customize, ensure the bot has what it needs for the features you intend to use. Using the "Administrator" permission (integer `8`) is the simplest but grants broad access. A more tailored permissions integer is often preferred for security.

## After Inviting

Once the bot is in your server, an administrator can proceed with [Server Configuration](server-config.md) to set up specific channels and roles.