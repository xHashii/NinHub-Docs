# Moderator Commands

These commands are typically restricted to users with a designated Moderator role (configured via `/server_config`) or server administrators.

## Report a 1v1 Match Result

*   **Command:** `/report`
*   **Description:** Used by moderators to report the outcome of a 1v1 match.
*   **How to use:**
    ```discord
    /report winner:@WinnerName loser:@LoserName mvp:@MVPName (optional)
    ```
*   **What happens:**
    *   If your server has "Public Match Confirmation" enabled (default), the reported loser will receive a message with buttons to "Confirm" or "Dispute" the result. ELO changes apply after confirmation or auto-confirmation after a timeout.
    *   If "Public Match Confirmation" is disabled, ELO changes are applied immediately.
    *   The match result is logged and will appear in player profiles and match history.

## Start a Team Match (Matchmaking)

*   **Command:** `/startmatch`
*   **Description:** Initiates a team match. Can randomly select players from a configured lobby voice channel or use specified players. Automatically creates dedicated voice channels for each team.
*   **How to use:**
    *   **Random Lobby Mode:**
        ```discord
        /startmatch players_per_team:<number> 
        ```
        *(Example: `/startmatch players_per_team:2` for a 2v2. Players must be in the pre-configured lobby VC.)*
    *   **Preset Party Mode:**
        ```discord
        /startmatch players_per_team:<number> alpha_player1:@PlayerA1 alpha_player2:@PlayerA2 beta_player1:@PlayerB1 beta_player2:@PlayerB2
        ```
        *(Adjust `alpha_playerX` and `beta_playerX` arguments based on `players_per_team`.)*
*   **What happens:** Selected players are moved to new "Team Alpha VC" and "Team Bravo VC" voice channels. An announcement is made in the channel where the command was used.
*   **Note:** Requires server admin to configure "Lobby VC" and "Match Category" using `/server_config` first.

## End a Team Match & Report Winner

*   **Command:** `/endmatch`
*   **Description:** Ends an active team match, reports the winning team, and optionally an MVP. Calculates and applies ELO changes for all participants and cleans up match voice channels.
*   **How to use:**
    ```discord
    /endmatch winning_team:<Team Alpha or Team Bravo> mvp_player:@PlayerName (optional)
    ```
*   **What happens:** Team voice channels are deleted, players are typically moved back (behavior may depend on server setup), ELO is updated for all participants, and a match summary is posted.

## Clean Up Match Channels (If Needed)

*   **Command:** `/cleanmatchchannels`
*   **Description:** Manually deletes any orphaned team match voice channels if `/endmatch` failed to do so (e.g., due to a bot restart or error).
*   **How to use:**
    ```discord
    /cleanmatchchannels
    ```
*   **What happens:** The bot attempts to find and delete voice channels named according to the team name settings (default: "Team Alpha VC", "Team Bravo VC") within the configured match category.