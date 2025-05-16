---
date: '2025-05-16T09:53:49+10:00'
title: 'Q3Test Bots'
---

Before Quake3 was released there were public test versions. And before that there was a leaked IHV version.

I acquired and played all of them.

I remember spending a lot of time trying to get bots working with one of these releases.

It may have been the q3test.

We had to run a command that modified the game, then we could use commands to spawn bots. The fun was figuring out what all the bot commands did.

The bots were no good, but we had a lot of fun with it all.

I remember chatting in the [shuga shack forums](https://web.archive.org/web/19991001204309/http://www.shugashack.com/msgboard/quake1.htm) about all of this at the time. The specific threads may not have been archived sadly.

Let's dig in.

I [found](https://discmaster.textfiles.com/browse/23382/Chip_1999-12_cd.bin/servis/tipy/web/soubory/q3tbots.zip) `q3tbots.zip` that contains `q3tbots.txt` and `q3tbots.exe`:

```text
-rw-rw-r--  0 0      0        2564 31 May  1999 q3tbots.txt
-rw-rw-r--  0 0      0       32768 31 May  1999 q3tbots.exe
```

Here's the header of the readme:

```text
05/31/1999
================================================================
Title                   : Q3Test Bots Galore
Filename                : q3tbots.exe
Author                  : YoGrE
Email Address           : yogre@hotmail.com
Description             : Enables Bots in Quake 3 Test
================================================================
```

That's right.

YoGrE figured it out and we were all chatting on the shuga shack message board.

It says it was for the Q3Test and is dated May 31 1999.

I suspect that this was the Q3Test v1.05.

It seems that this patch was replaced by an easier method:

```text
Thanks to YoGrE, we don't need this exe patching thing anymore.
Just rename your demoq3 folder to baseq3 and put this named
productid.txt <http://quake.at.frob.org/files/misc/productid.txt>
into baseq3 .
```

-- [Unofficial Quake 3 Arena Test FAQ](https://groups.google.com/g/alt.games.quake3/c/jXvkX7la-UQ), alt.games.quake3, 4 Sept 1999.

I also found this:

```text
Bots are back!

Bots dont work on 106/7/8

so you need to get 105 from the Q3TESTfiles page first

Then get the q3bots 1.1 here..

q3bots1.1
```

-- [http://www.moneychair.demon.co.uk/quake3/qbots.htm](https://web.archive.org/web/20000601060651fw/http://www.moneychair.demon.co.uk/quake3/qbots.htm) (archived)

It suggests an updated version of `q3tbots.zip` as `q3tbots-1.1.zip` or `q3tbots-1_1.zip`.

It also confirms that bots only worked with Q3Test v1.05.

Some more (broken) links:

* ftp.incubus.net/incoming/q3tbots-1.1.zip
* ftp://ftp.dermak.pl/incoming/botq3a/q3tbots.zip
* ftp://ftp.fps3d.com/quake3/q3tbots.zip
* ftp://ftp.pc.com.pl/pliki/zip/q3tbots.zip
* ftp://ftp.xaos.ru/pub/quake3/bots/q3tbots.zip
* http://hellborn.virtualave.net/q3tbots.zip
* http://members.xoom.com/synmaps/q3tbots.zip
* http://privat.schlund.de/e/elk-clan/q3/q3tbots.zip
* http://q3.zone.ru/files/q3tbots.zip
* http://www.moneychair.demon.co.uk/quake3/q3bots/q3tbots-1_1.zip
* http://www.multiplayer.it/files/q3tbots.zip
* http://www.q3arena.pl/download/add/q3tbots-1.11.zip
* http://www.tranzmit.connectfree.co.uk/q3bots.zip
* https://riva.pepak.net/soubory/q3tbots.zip
* And on...

A copy of the v1.1 readme was posted on Usenet:

```text
==============================================================
05/31/1999
================================================================
Title : Q3Test Bots Galore
Filename : q3tbots.exe
Version : 1.1
Author : YoGrE
Email Address : yo...@hotmail.com
Description : Enables Bots in Quake 3 Test
================================================================

* Credits *

- id Software for most everything they did and mostly for leaving most of
the bot code intact :)

* Installation *

Run the q3tbots.exe file in your q3test directory. It will backup the
original
and create a patched file.. As far as I know, everything works fine but I
may
be wrong.

Start Q3Test and load a map.

Type "nav gen" in the console. This will create a navigation file the bots
need
to operate. This takes a VERY long time to complete and it will seem like
your
computer has hung. On my P2 300 it takes about 2-3 minutes I think. This
needs
to be done only once for each map you plan on playing bots in.

* Running *

Start Q3Test and load a map. In the console, type: "bot spawn <botname>"

Botname is a bot name from the scripts/bots.txt file. It is optional and
will spawn a bot named "Player" if not specified.

You can also edit the arenas.txt file for pre-defined arenas.

* Notes *

As many of us have known for some time, the game dll contains the bot code
but it
was disabled. After getting frustrated with my poor connection (28.8) I
decided
to see if I could somehow re-enable it. Guess what? It worked :)

I am not sure if I have enabled everything but it seems to work. I have
played a
little on both maps and the bots seem pretty good. I haven't played enough
to give
an accurate assessment though. I leave that to you :)

It's not perfect. It seems the bots will only use the MachineGun. This could
be because
weapon switching is not programed yet but it may be related to the bots.cfg
file.

* History *

Version 1.1
- bots.cfg now loads correctly. Bots still use only MG as far as I can tell.
Maybe someone can mess with the bots.cfg parameters a bit. As far as I can tell,
these are the possible params a bot can have:

model
reactions
aim
move
aggression
intelligence
hfov
vfov
healthMethod
armorMethod
ammoMethod
weapons
snd

Let me know if you figure something (other than the obvious) out so I add
it to the
txt file.

- The "nav gen" doesn't need to be repeated if you already installed the old
version
and did it once.

- New version can be used against patched dll. File is backed up as
extension b11
(instead of bak) to avoid loss of original file.

* Disclaimer *

I know of no way this file can harm your computer, however, I cannot be held
responsible if it does. If you choose to use it in any way, you do so under
your own risk.

* Copyright / Permissions *

This file may be electronically distributed only with no
charge to the recipient, and may not be modified in any way.
This text file must be included with the map unmodified.

This file may not be distributed on any CD-ROM without the
prior, explicit written consent by YoGrE.
```

-- [alt.games.quake3](https://groups.google.com/g/alt.games.quake3/c/6JVRn8dLmd4/m/oMNPaiQmYE0J), 6 July 1999.


I created a geocities site to document all my findings and shared the link on usenet:

```text
What do you think?, 4 Nov 1999

Check out my webpage, what do you think?
Do I need to change/add/remove anything?
BTW there is a lot of info on q3bots!
http://geocities.com/q3bots/
-ChoppeR-
```

-- [alt.games.quake3](https://groups.google.com/g/alt.games.quake3/c/ccjVDoyjZ84/m/ElB0HqBI3GcJ)

Sadly, it was not archived.



