### Operating Modes in Cisco IOS

"Operating Modes in Cisco IOS" refers to the different modes or levels of operation that are available within the Cisco Internetwork Operating System (IOS). These modes determine the level of access and the types of commands that can be executed on a Cisco networking device, such as routers and switches. The main operating modes in Cisco IOS include:

#### User EXEC Mode:

- **Description:** Provides basic monitoring commands.
- **Command:** `hostname>`

#### Privileged EXEC Mode:

- **Description:** Offers full control over device configurations.
- **Command:** `hostname#` (Requires entering from User EXEC Mode using `enable` command and providing the enable password if configured)

#### Global Configuration Mode:

- **Description:** Allows changes to device settings.
- **Command:** `hostname(config)#` (Requires entering from Privileged EXEC Mode using `configure terminal` command)
