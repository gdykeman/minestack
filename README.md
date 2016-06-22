MineStack
=========
OpenStack Heat Template to deploy Minecraft on a node. Uses Ansible role from
[this repo](https://github.com/hhoover/minecraft-role).

Parameters
==========
Parameters can be replaced with your own values when standing up a stack. Use
the `-P` flag to specify a custom parameter.

* `minecraft_gamemode`: Game Mode for Minecraft.  0 - Survival, 1 - Creative, 2 - Adventure, 3 - Spectator (Default: 1)
* `minecraft_difficulty`: Difficulty level for Minecraft.  0 - Peaceful, 1 - Easy, 2 - Normal, 3 - Hard (Default: 2)
* `minecraft_monsters`: Enable or disable spawning of hostile mobs (Default: True)
* `minecraft_hardcore`: Enable or disable Hardcore mode.  In Hardcore mode, users will be banned from the server upon death (Default: False)
* `minecraft_animals`: Enable or disable spawning of passive mobs (Default: True)
* `minecraft_npcs`: Enable or disable spawning of villagers (Default: True)
* `minecraft_motd`: Message to be displayed in the server list (Default: A Minecraft Server)
* `minecraft_max_players`: Maximum number of players able to connect at any given time (Default: 20)
* `minecraft_online`: Online mode requires clients to have a valid Minecraft account. (Default: True)
* `instance_flavor`: Flavor of OpenStack Instance to use for Minecraft (Default: m1.medium)
* `instance_image`: Image to use for the OpenStack Instance. (Default: ubuntu_1404_server_cloudimg_amd64)
* `public_net_id`: The UUID of your Provider Network in Neutron. Needed for a Floating IP address.

Outputs
=======
Once a stack comes online, use `heat output-list <STACKNAME>` to see all available outputs.
Use `heat output-show --format raw <STACKNAME> <OUTPUT>` to get the value of a specific output.

* `minecraft_ip`: Floating IP
* `ssh_private_key`: SSH Private Key
