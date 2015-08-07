NAME
====

**virgil** -- command line tool for using Virgil Security stack
functionality.

SYNOPSIS
========

**virgil** *command* [*command\_opts*] [*command\_args*]

DESCRIPTION
===========

The **virgil** program is a command line tool for using Virgil Security
stack functionality. It can be used to encrypt, decrypt, sign and verify
data. Functionality also includes interaction with Virgil Public Keys
Service.

COMMANDS
========

**keygen**  
Generate private key with a given parameters. For example:

    virgil keygen -o user.key

**key2pub**  
Get public key from the private key. For example:

    virgil key2pub -i user.key -o user.pub

**keyreg**  
Register user's public key on the Virgil Public Keys service. For
example:

    virgil keyreg -i user.pub -o user.pk email:user@domain.com

**keyget**  
Get user's public key from the Virgil Public Keys service. For example:

    virgil keyget -o user.pk email:user@domain.com

**confirm**  
Send confirmation code to the Virgil Public Keys service. For example:

    virgil confirm -i email:user@domain.com -c E5J8W7

**reconfirm**  
Resend confirmation code to the user for given user's identifier. For
example:

    virgil reconfirm -i email:user@domain.com

**encrypt**  
Encrypt data for given recipients which can be defined by Virgil Public
Keys and by passwords. For example:

    virgil encrypt -i plain.txt -o encrypted.dat email:user@domain.com

**decrypt**  
Decrypt data for given recipient which can be defined by Virgil Public
Key or by password. For example:

    virgil decrypt -i encrypted.dat -o plain.txt -k user.key -r user.pk

**sign**  
Sign data with Private Key. For example:

    virgil sign -i plain.txt -o plain.txt.sign -k user.key

**verify**  
Verify data with Virgil Public Key. For example:

    virgil verify -i plain.txt -s plain.txt.sign -r key:user.pk
    virgil verify -i plain.txt -s plain.txt.sign -r email:user@domain.com

SEE ALSO
========

`virgilkeygen(1)`, `virgilkey2pub(1)`, `virgilkeyreg(1)`,
`virgilkeyget(1)`,  
`virgilconfirm(1)`, `virgilreconfirm(1)`,  
`virgilencrypt(1)`, `virgildecrypt(1)`,  
`virgilsign(1)`, `virgilverify(1)`