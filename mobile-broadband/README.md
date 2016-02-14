= Mobile broadband setup

Some huawei CDC NCM devices are one step away from being used for mobile access.
The following files have been tested with:

 * Huawei E5786s-32a (Domino Orange LTE-A)
 * Huawei E5377s-32

== Useful AT commands

Attaching/Unlocking PIN code.

> AT\r\n
> ATZ\r\n
> AT+CPIN=1234\r\n 

Setting up the modem behaviour.
ATQ0 => Modem is not quiet
ATV1 => Modem is verbal (replies with word messages) 
ATE1 => Local echo enabled
ATS0 => Disable auto-answer (=0)

> ATQ0 V1 E1 S0=0

Creating the bearer without credentials

> AT^NDISDUP=1,1,"apn"\r\n

Creating the bearer with credentials

> AT^NDISDUP=1,1,"apn","user","password"\r\n

Destroying the bearer

> AT^NDISDUP=1,0
