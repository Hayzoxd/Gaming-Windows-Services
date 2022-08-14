# List of required services for some games.

__Battle.net:__
* Wcmsvc

__FIFA 22:__
* Wcmsvc
* nsi

__Fortnite:__
* Null

__Grand Theft Auto V:__
* mssmbios

__Call of Duty: Modern Warfare:__
* nsi

__Tom Clancy's Rainbow Six: Siege:__
* nsi

__Rocket League:__
* Winmgmt
* nsi

---

Here are several examples of .bat files to launch your games and their necessary drivers. Change the driver and the path to use with other games.

__FIFA22.exe__
@echo off
sc config Wcmsvc start=demand
sc config nsi start=demand
sc start Wcmsvc
sc start nsi
"E:\Program Files\FIFA 22\FIFA22.exe"
sc config Wcmsvc start=disabled
sc config nsi start=disabled
exit

__ModernWarfare.exe__
@echo off
sc config nsi start=demand
sc start nsi
"E:\Program Files\Call of Duty Modern Warfare\ModernWarfare.exe"
sc config nsi start=disabled
exit

__FortniteClient-Win64-Shipping.exe__
@echo off
sc config Null start=demand
sc start Null
"D:\Program Files\Fortnite\FortniteGame\Binaries\Win64\FortniteClient-Win64-Shipping.exe"
sc config Null start=disabled
exit

__RocketLeague.exe__
@echo off
sc config Winmgmt start=demand
sc config nsi start=demand
sc start Winmgmt
sc start nsi
"D:\Program Files\rocketleague\Binaries\Win64\RocketLeague.exe"
sc config Winmgmt start=disabled
sc config nsi start=disabled
exit
