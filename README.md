# Elevate_task_4
Firewall setup on Linux os
On Linux (using UFW)
 * Open Terminal and Check UFW Status:
   * Open a terminal.
   * Check if UFW is installed and enabled by running the command:
     sudo ufw status

   * If UFW is not active, you can enable it with:
     sudo ufw enable

 * List Current Firewall Rules:
   * To see a numbered list of all rules, use:
     sudo ufw status numbered

   * This will show you the rules currently in effect.
 * Add a Rule to Block Inbound Traffic:
   * To block incoming traffic on port 23 (Telnet), use the following command:
     sudo ufw deny 23/tcp

   * This command adds a rule to deny all TCP traffic on port 23.
 * Test the Rule:
   * From another computer on the same network, try to connect to the Telnet port of your Linux machine.
   * The connection should be blocked by UFW.
 * Add Rule to Allow SSH (port 22):
   * To ensure you don't lock yourself out of your system, you can add a rule to allow SSH traffic (if it isn't already enabled by default).
   * Run the command:
     sudo ufw allow 22/tcp

   * You can also specify "ssh" directly, as UFW recognizes common services:
     sudo ufw allow ssh

 * Remove the Test Block Rule:
   * To remove the rule blocking Telnet, you need to find its number in the numbered status list. Run:
     sudo ufw status numbered

   * Look for the rule that says DENY IN 23/tcp. Let's say its number is 3.
   * To delete it, run:
     sudo ufw delete 3

   * This will remove the block rule and restore the original state.
