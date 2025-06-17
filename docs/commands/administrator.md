# Administrator Commands

These commands are typically restricted to server administrators.

## Configure Server Settings

*   **Command:** `/server_config`
*   **Description:** Allows admins to set up or view bot settings for the server. This includes the matchmaking lobby VC, the category for match VCs, the moderator role for bot commands, the audit log channel, and public match confirmation preferences.
*   **How to use:**
    *   To view current settings:
        ```discord
        /server_config
        ```
    *   To set specific options (only provide the ones you want to change):
        ```discord
        /server_config lobby_vc:#voice-channel match_category:CategoryName mod_role:@RoleName audit_log_channel:#text-channel public_match_confirmation:True
        ```
*   **What happens:** Bot settings are updated for your server. These settings are crucial for features like automated matchmaking, ELO logging, and moderator permissions.

## Set Marketplace Notification Channel

*   **Command:** `/set_marketplace_channel`
*   **Description:** Designates a specific text channel where NinHub will post notifications about new listings from the website's marketplace.
*   **How to use:**
    ```discord
    /set_marketplace_channel channel:#your-market-channel
    ```
*   **What happens:** The bot creates a webhook in the specified channel to send marketplace updates. The bot needs "Manage Webhooks" permission in that channel.

## Disable Marketplace Notifications

*   **Command:** `/disable_market_notifications`
*   **Description:** Stops marketplace notifications from being sent to your server and removes the associated webhook.
*   **How to use:**
    ```discord
    /disable_market_notifications
    ```
*   **What happens:** The bot removes the marketplace webhook from your server.

## Create a Nindex (Shared Intel Group)

*   **Command:** `/nindex_create`
*   **Description:** Creates a new Nindex for a specific group (e.g., a corporation, team, or study group) within your server. Access to view and manage the Nindex on the website is controlled by the Discord roles you specify.
*   **How to use:**
    ```discord
    /nindex_create name:"Your Nindex Name" member_role:@MemberViewRole leader_role:@ManagerRole
    ```
    *(Example: `/nindex_create name:"Akatsuki Intel" member_role:@AkatsukiMember leader_role:@AkatsukiLeader`)*
*   **What happens:** A new Nindex is registered with the NinHub platform. Users in your Discord server who have the specified "Member Role" or "Leader Role" will be able to access and contribute to this Nindex on the website. Leaders can manage entries and members.