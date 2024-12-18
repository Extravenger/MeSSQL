# MeSSQL

MeSSQL is a high-speed, efficient tool designed for interaction and exploitation of Microsoft SQL (MSSQL) servers within a domain. Built with offensive security in mind, MSSoniQL enables penetration testers and red teamers to execute various tasks on MSSQL servers, both local and remote, with a focus on speed and ease of use.

# Features

### Impersonation Capabilities:

- Execute as a login using `EXECUTE AS LOGIN` within the current MSSQL instance.
- Execute as a user using `EXECUTE AS USER` within the current MSSQL instance.

### Linked Server Interaction:

- Run commands on linked servers using EXEC AT LinkedServer, providing seamless interaction across SQL environments.

### Exploitation Modules:

- Perform xp_dirtree to trigger SMB requests and potentially capture credentials via tools like Responder.

### User Management:

- Create a new sysadmin login either on the local MSSQL instance or on a linked server for extended control and persistence.

# Installation

Clone the repository and build:  

    git clone https://github.com/yourusername/MSSoniQL.git  

Or just download the compiled binary from Releases page.

# Usage

When you run MeSSQL, you will be able to provide the server name, database name, username and password to connect with.  
If you leave the username and password blank, Windows Authentication will take place instead.  
Once a connection established - you'll be presented with a menu:

    [+] Choose an option:

    1. Impersonate a login (EXECUTE AS LOGIN in current instance)
    2. Impersonate a user (EXECUTE AS USER in current instance)
    3. Execute command on a linked server (EXEC AT LinkedServer)
    4. Perform xp_dirtree
    5. Create new sysadmin user (local/remote)

# Menu Options:

- Impersonate a Login

        Allows you to impersonate a specific login in the current MSSQL instance using EXECUTE AS LOGIN.
        Useful for privilege escalation or testing roles assigned to a specific login.

- Impersonate a User

        Similar to option 1 but focuses on impersonating database users with EXECUTE AS USER.
        Ideal for exploring privileges and testing user-level permissions.

- Execute Command on a Linked Server

        Lists available linked servers and allows you to execute commands on the selected server.

- Perform xp_dirtree

        Executes xp_dirtree to generate SMB requests to a target IP address.
        Can be used for credential theft or to force authentication via SMB to tools like Responder.

- Create New Sysadmin User

        Creates a new sysadmin login either on the current MSSQL instance or a linked server.
        Useful for establishing persistence and administrative control.

# ToDo

--
