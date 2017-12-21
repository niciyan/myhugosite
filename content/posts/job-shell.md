---
title: "Job Shell"
date: 2017-12-21T17:34:36+09:00
draft: false
---

my shell snippets.

    # view other login user
    w

    # view own teletypewriter
    tty

    # view host's working time
    uptime

    # view listening port ( TCP, UDP, unix socket  respectively )
    netstat -tnl
    netstat -unl
    netstat -xnl

    ###########################
    #   Apache Log grep
    ###########################
    # limit by date (calendar)
    grep "08/Dec/2007"

    # limit by hour (example: 22 o'clock)
    grep "08/Dec/2007:22:"


    # get DNS server
    cat /etc/resolv.conf ( grep "nameserver" )

    # view services
    systemctl list-unit-files -t service | grep "enabled"

    # ZABBIX
    zabbix_get -s $AGENTIP -k system.cpu.util[,,avg5]
    zabbix_get -s $AGENTIP -k vm.memory.size[pavailable]

    # MEMO ##############################
    #
    # server-sns AWS profile 
    # IAM username : member
    #
    # MEMO ##############################
