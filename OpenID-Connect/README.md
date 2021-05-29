# How OIDC and SRAM can make SURF prevail
SURF has many services used in building and maintaining data infrastructure. The most common used is SURF-conext which is the authenticator of many institutes and Universities. 
Conext uses the OpenID-connect extension for the OAuth2.0 authentication protocol. This means that by using this service it is possible to identify a user that wishes to access a restricted site. 
Surf Research Access management is another of service comparable to the restricted access that Conext provides. With SRAM however, admins are able to assign certain roles to the researchers. Lets say that there is a shared data analysis platform and data storage, then you wouldm't want everyone to have access to all of it. Some areas would be locked and could be opened when the role of the reasearcher is changed.

## How OIDC be implemented in Galaxy?
For this a schematic overview was made to connect galaxy to such a system
![alt text](https://github.com/NielsMol/UNRAVEL-Galaxy/blob/main/OpenID-Connect/Dataflow%20of%20applicant.png )

## How could the EGA be implemented in Galaxy?
For this a schematic overview was made to connect galaxy to such the EGA and how dataflow would work
![alt text](https://github.com/NielsMol/UNRAVEL-Galaxy/blob/main/OpenID-Connect/Overflow%20of%20the%20data%20management.png)

## How could homomorphic encryption work for Galaxy?
This option is yet to be fully explored but this overview would be the ideal option
![alt text](https://github.com/NielsMol/UNRAVEL-Galaxy/blob/main/OpenID-Connect/homomorhpic%20encryption%20basic%20overview.png)
