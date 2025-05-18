---
date: '2025-05-16T09:53:49+10:00'
title: 'Q3Test Bots'
---

Before Quake3 was released there were public test versions. And before that there was a leaked IHV version.

I acquired and played all of them.

I remember spending a lot of time trying to get bots working with one of these releases.

It may have been the q3test v1.05.

We had to run a program that modified the game, then we could use commands in-game to spawn bots. The fun was figuring out what all the bot commands did.

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

...
```

That's right...

YoGrE figured it out and we were all chatting on the shuga shack [messageboard](https://web.archive.org/web/19991114183603/http://shugashack.com:80/msgboard/quake3.htm).

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

I [found a working link](https://web.archive.org/web/20120309021345/http://www.fortunecity.com/underworld/olympic/452/downloads/q3tbots-1.1.zip) for v1.1.

Here's the content:

```text
-rw-rw-r--  0 0      0        3305  1 Jun  1999 q3tbots.txt
-rw-rw-r--  0 0      0       32768  1 Jun  1999 q3tbots.exe
-rw-rw-r--  0 0      0         248  8 Jun  1999 Readme.txt.txt
```

It seems `Readme.txt.txt` was added by whoever hosted the file.

Here's the truncated file header and changelog:

```text
05/31/1999
================================================================
Title                   : Q3Test Bots Galore
Filename                : q3tbots.exe
Version                 : 1.1
Author                  : YoGrE
Email Address           : yogre@hotmail.com
Description             : Enables Bots in Quake 3 Test
================================================================

...

* History *

Version 1.1
- bots.cfg now loads correctly. Bots still use only MG as far as I can tell. Maybe
  someone can mess with the bots.cfg parameters a bit. As far as I can tell, these
  are the possible params a bot can have:

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

  Let me know if you figure something (other than the obvious) out so I add it to the
  txt file.

- The "nav gen" doesn't need to be repeated if you already installed the old version
  and did it once.

- New version can be used against patched dll. File is backed up as extension b11
  (instead of bak) to avoid loss of original file.
```

For future reference, here are some historical locations for `q3tbots.zip` (some were archived):

* ftp://ftp.dermak.pl/incoming/botq3a/q3tbots.zip
* ftp://ftp.fps3d.com/quake3/q3tbots.zip
* ftp://ftp.pc.com.pl/pliki/zip/q3tbots.zip
* ftp://ftp.xaos.ru/pub/quake3/bots/q3tbots.zip
* http://frefrafac.quakecity.net/download/utils/q3tbots.zip
* http://hellborn.virtualave.net/q3tbots.zip
* http://mapzone.quake3nation.com/files/q3tbots.zip
* http://members.xoom.com/synmaps/q3tbots.zip
* http://people.a2000.nl/tscheff/q3tbots.zip
* http://privat.schlund.de/e/elk-clan/q3/q3tbots.zip
* http://q3.zone.ru/files/q3tbots.zip
* http://q3.zone.ru/files/q3tbots.zip
* http://riva.hardware.ru/soft/util/hack/q3tbots.zip
* http://riva.pepak.net/soubory/q3tbots.zip
* http://src.doc.ic.ac.uk/packages/idgames2/planetquake/captured/wfbots/q3tbots.zip
* http://www.captured.com/underground/news/q3tbots.zip
* http://www.d128.com/files/q3tbots.zip
* http://www.fortunecity.com/underworld/ninja/228/files/q3tbots.zip
* http://www.fortunecity.com/underworld/tactic/865/q3tbots.zip
* http://www.multiplayer.it/files/q3tbots.zip
* http://www.quake.cz/mvs/ostatni/q3tbots.zip
* http://www.quake.de/FILES/quake3/tool/q3tbots.zip
* http://www.quake.wplus.net/archiv/q3tbots.zip
* http://www.tranzmit.connectfree.co.uk/q3bots.zip
* https://www.penza-games.narod.ru/Q3tbots.zip

Here are some historical locations for `q3tbots-1.11.zip`  (some were archived):

* ftp://ftp.incubus.net/incoming/q3tbots-1.1.zip
* http://members.xoom.com/JuDa5/q3tbots-1.1.zip
* http://www.fortunecity.com/underworld/olympic/452/downloads/q3tbots-1.1.zip
* http://www.moneychair.demon.co.uk/quake3/q3bots/q3tbots-1_1.zip
* http://www.q3arena.pl/download/add/q3tbots-1.11.zip

Some discussion here:

* [http://riva.pepak.net/archiv/99_06.htm](http://riva.pepak.net/archiv/99_06.htm)
* [http://www.penza-games.narod.ru/progi.htm](http://www.penza-games.narod.ru/progi.htm)
* [http://q3.zone.ru/sections/general/bots/bots.html](https://web.archive.org/web/19991111063239/http://q3.zone.ru:80/sections/general/bots/bots.html) (archived)
* [/servis/tipy/web/files.htm](https://discmaster.textfiles.com/view/23382/Chip_1999-12_cd.bin/servis/tipy/web/files.htm) (archived)
* [http://www.q3arena.pl/1707-1209.html](https://web.archive.org/web/20010222142817/http://www.q3arena.pl/1707-1209.html) (archived)
* [http://www.tranzmit.connectfree.co.uk/quake3.htm](https://web.archive.org/web/19991009060531/http://www.tranzmit.connectfree.co.uk/quake3.htm) (archived)
* [http://www.moneychair.demon.co.uk:80/quake3/qbots.htm](https://web.archive.org/web/20000601060651/http://www.moneychair.demon.co.uk:80/quake3/qbots.htm) (archived)

Interestingly, an alternate version (ripped off?) was shared here:

* https://www.geocities.ws/dinkhotline/q3/bot.zip

Here's the readme header:

```text
29/Aug/99
================================================================
Title                   : Q3Test Bots from quakemania
Filename                : q3tbots.exe
Version                 : 1
Author                  : Locutus[x]
Email Address           : quake_mania@hotmail.com
Description             : Enables Bots in Quake 3 Test
Web site                : Http://www.quakemania.freeserve.co.uk/
================================================================

...
```


Finally, I created a Geocities site to document all my findings for how to get bots working and how to configure them correctly, and shared the link on Usenet:

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

Update: [See here](/blog/posts/chopper-land/) for an archived version of my old site.

Update: [See here](/blog/posts/q3-test-versions/) for a list of all q3test versions. The above mod was for Q3Test v1.05.

