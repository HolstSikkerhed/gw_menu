# gw_menu

Tiny replacement for system shells on secure gateway machines.

Allows untrusted users to run a few commands without being able to 
specify arguments, and it allows users to connect to hostnames
specified in the menu.hosts file.

1. Install `gw_menu` to where your other shells are.
2. Add the full path to the system `/etc/shells` file
3. Copy the HELP, HOSTS and GREETING files to `/etc/gw_menu`
4. Tweak HELP, HOSTS and GREETING to fit your environment.
5. Add users with their shell set to `gw_menu`
Simply add the short hostname to `HOSTS`, and use the system-wide ssh_config
to specify full hostnames, if needed. An example usage session follows:


```
$ ssh gateway.example.com
Unauthorised access prohibited.

  Contact: http://security.example.com/ -- security@example.com
Helpfiles: http://security.example.com/help/gateways/

Enter command or host name, or 'help' for help.  

gateway> help
Type a legal command or hostname at the prompt.

Available commands:

        help            -- this menu
        uptime          -- display system uptime and load averages
        who, w, finger  -- display information about connected users
        exit            -- disconnect from the system (aliases: bye,
                           logout, quit)

Available hostnames:

	webserver buildhost fileserver 

gateway> uptime
 2:47PM  up  2:24, 4 users, load averages: 0.09, 0.09, 0.08
gateway> webserver
webserver$ 
```
