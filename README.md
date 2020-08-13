# isudo — `sudo -i` wrapper

## Overview
`isudo` automates simple routine operation in case when you login to a server as some user, then use `sudo -i -u <username>` to re-login as a different user.
It does the following:
- executes `sudo -l`
- finds out the list of users which current user can execute **all** commands **without a password**
- filters only existing users
- prompts for user using `readline(3)` (autocomplete is supported)
- executes `sudo -inu <selected user>` (or `sudo -nu <selected user> -- /bin/bash` if login is disabled for user)

## Requirements
- Python 2.7, Python 3.4+
- Tested on CentOS 7
