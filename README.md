# SWTG118AS and SWTG115AS RE

# Web UI

## Factory CGI

> Factory CGI can be accessed directly via the admin credentials

| CGI        | Description      |
| ---------- | ---------------- |
| ftdft.py   | Factory Defaults |
| ftlogo.py  | Factory Logo     | 
| ftcolor.py | Factory Colours  |

## Passwords

| User        | Password        | Internal MD5 Hash                | CGI          |
| ---------- | ---------------- | -------------------------------- | ------------ |
| admin      | admin            | f6fdffe48c908deb0f4c3bd36c032e72 | login.cgi    |
| hengrui    |                  | 81d57ea79621e8887914f40ee4122185 | login_ft.cgi |

# Serial CLI

## Baudrate

|           | Unmanaged | Web Managed |
| --------- | --------- | ----------- |
| Speed     | 9600      | 57600       |
| Parity    | None      | None        | 
| Data-bits | 8         | 8           |
| Stop-bits | 1         | 1           |

## Boot Log

```bash
==========Loader start===========
Press any key to start the normal procedure.
To run SPI flash viewer, press [v]
To enforce the download of the runtime kernel, press [ESC] .....
  cmd -1
    Check Runtime Image.....
    Chksum Correct!
    RunTime Kernel Starting....  
Ver8373_72: C
Not rtl8221b and skip init flow...id = c849 
###SDS FW Load finished !!



===========================Config Area pre-check Starts.=====================.
Pre-Check the config size structure is equal or not.
(sizeof(configCache)) a36.
(FLSH_ADDR_END-FLSH_CONFIG_ADDR_START) a36. 
(FLSH_CONFIG_ADDR_START) 1fe000.
(FLSH_ADDR_END) 1fea36.
It seems no risk!..................
==============================Config Area pre-check ends.===================.



SalFlshCopyFlshToCache()
sal_sys_config_restore()
Restore dhcp state is: 0

Restore ip is: 192.168.2.1

...OK
sal_mirror_config_restore()...OK
sal_qos_config_restore()...OK
sal_vlan_config_restore()...OK
sal_rate_config_restore()...OK
sal_trunk_config_restore()...OK
sal_l2_config_restore()...OK
sal_loop_config_restore()...OK
sal_eee_config_restore()...OK
sal_stp_config_restore()...OK
sal_igmp_config_restore()...OK
sal_port_config_restore()...OK



#############According to the flash setting to set the WEB/DUMB mode

#############Read the web/dumb mode.....!!!###

#############web_dumb_cfg.vld_flag=-1, web_dumb_cfg.mode=-1
#############Begin to set the web mode



################################################################

############Login Menu ############
### Please input uboot password below: ###

```

## Password

The *"uboot"* password is `Switch321`

## Commands

* `gpio`
* `stp`


## SPI Flash Viewer

```bash
=========================SPI FLASH VIEWER=============================
    b: reboot
    e <addr>: Erase flash with the address of <addr>
    ev <addr>: Erase flash with the address of <addr> and then Verify
    r <addr> <len>: read flash from the address of <addr> and then dump
    c: check runtime kernel without boot
    cb: check runtime kernel and boot if checksum is pass
    h: print header
    l: load runtime kernel
    v: show verobose information
    m: print this menu
    q: quit from spi flash view
>
```

## Protected Regions

```bash
There 2 protected region(s).
    Portected region 0: 0x000000-0x001000
    Portected region 1: 0x004000-0x01c000
```

# Tools

## Update Firmware Validator and Updater

[switchup.py](/tools/switchup.py)
