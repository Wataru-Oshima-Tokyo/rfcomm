# rfcomm
(on the server)

$ sudo rfcomm listen /dev/rfcomm0 1

(On the client)

Check the MAC address of the device connected via bluetooth

$ bluetotthctl

-----------------
[NEW] Controller 00:27:13:C9:30:15 wataru-ThinkPad-T410 [default]

[NEW] Device DC:A6:32:E4:E9:D8 ubuntu

[NEW] Device B8:27:EB:2C:38:E1 zumo

Agent registered

-----------------

And copy the target address ( in this case  DC:A6:32:E4:E9:D8)

# bind

sudo rfcomm bind 0  DC:A6:32:E4:E9:D8 1

# connect

$ sudo minicom -D /dev/rfcomm0


# release 

(On the server)

1. check the process number
2. kill it

$ sudo lsof |grep /dev/rfcomm0

/// show something followed by a 4 digit number such as 3294

$ sudo kill 3294

(3294 is a number obtained by the previous step)

(On the client)
$ sudo rfcomm release 0
