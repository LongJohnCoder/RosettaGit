+++
title = "Talk:Pierpont primes"
description = ""
date = 2019-09-25T20:13:32Z
aliases = []
[extra]
id = 22478
[taxonomies]
categories = []
tags = []
+++

== Scale back 2nd part? ==
Do I need to scale back the second part? (Find 250th primes). I don't want to have goals that are mostly unobtainable, If so, what would be a more reasonable number? 150th? 100th? --[[User:Thundergnat|Thundergnat]] ([[User talk:Thundergnat|talk]]) 23:55, 18 August 2019 (UTC)
::Hm, I would guess not, since there is a brute force Go version that works quickly. The way I wrote my entry is probably slow in general or slow for my language. I saw it done with prime factorizations on OEIS and thought it looked elegant. I'll give a different method a shot when I get to it. --[[User:Chunes|Chunes]] ([[User talk:Chunes|talk]]) 00:27, 19 August 2019 (UTC)
:::For languages with access to a quick/robust primality test, that is. Maybe it would be prudent to scale back a bit so that simpler primality tests can get the job done. --[[User:Chunes|Chunes]] ([[User talk:Chunes|talk]]) 00:30, 19 August 2019 (UTC)

:::It is very likely going to be much more efficient to generate Pierpont numbers and check if they are prime than to generate primes and check if they are Pierponts. --[[User:Thundergnat|Thundergnat]] ([[User talk:Thundergnat|talk]]) 01:20, 19 August 2019 (UTC)

:::: Essentially, this isn't going to help comparing   (one of Rosetta Code's objectives)   computer programming code,   in this case,   to find/display ginormous (Pierpont) primes,   ---   unless one has a robust   '''isPrime'''   function (mostly likely a BIF).   There is nothing to learn about <u>using</u> an   '''isPrime'''   BIF.   Otherwise, it's just an exercise in <strike>wasting</strike> consuming electric power.   Interpretive computer programming languages will have a large/largish obstacle to overcome with a brute force approach.   This shouldn't be the hurdle to jump over, just because interpretive languages have that handicap.     -- [[User:Gerard Schildberger|Gerard Schildberger]] ([[User talk:Gerard Schildberger|talk]]) 05:52, 19 August 2019 (UTC)

:::::I don't know; for a very large percentage of the time, choosing the right algorithm makes a much bigger difference to how fast things get done than the execution speed of the underlying language. Yeah, having a good library can make things easier, but it's not everything. Personally, I think it can be very instructive to see how different languages deal with and/or work around difficult problems. Just for my own amusement, I went and re-implemented this using no built-in <strike>factoring</strike> primality testing, and no outside libraries. Uses a modified version of the [[Miller–Rabin_primality_test#Perl_6]] with 100 rounds (which is what the Perl 6 built-in routine uses). It still finishes in around 12 seconds on my system; slower than the ~6 seconds using built-ins and ~1.5 seconds using optimized libraries, but still, not too bad. And to be fair, Perl 6 has been called many thing, but blazin' fast is not usually one of them.

:::::Even in an on-line limited and throttled VM it finishes in (slightly) less than 30 seconds.  <span style="background-color:yellow;">[https://tio.run/##lVRNb9pAED3Dr5gip7HBrIxJ2gSLKOohUg@VemhPhESbeF1cf6xlLwGU0D/WW/8YnV1sWBuUtIuQ1zPz3ny8XWcsjz9sNskKPnEeQzKPRQjF/AHC4j7Lw4SZn1MBRmqDekYwhoHjWKCtZ8iZmOcp3NC4YB6s26@wua8Q1dm@5fO3yLalwWLGcoZA4x6uwAWa@nJ7gtt1M9tzu4V8yuajDcF9GHh7Y4FGx2u3W4tZGDMZdCJ5ENbCvR8@jcH15EvR6@FzjZEBz8F0gZA7pLNIFj5GphFZ0L8CgyokkhtLJGbLLOG@aVAbiW0ZLTO1UrYUEAYqBssE5Ntuq@owRiYZbHMUirNVY1za4JaE6NLl0IiVL6aFlmzXP3ZyFPdOD5Ld6uK00SD1yEKWZxzHZxpilSG0gEeereTM5cSlqj@oQJHKF7kCGsbQ@Z5GKV@kIGEjUGgCX@ZY4gMDnuI/wLZNnwUU1bfkaNyOKk0lktUNXlCQilXQiKFcu4Bt25W3tEF/UIvQ8IWgAlXP@HB7Dhp26vt9WdUYhk3fdShYTgXP5QmauPaZfYFyEehOSeWxYTK0L233Y9OBCldkeFSuZ4zKs7ln/PObZPM4lqm10JjzTBtoiTYiJgevSEhGw7wgSZia0CVPNJ4zsAgGeAcojKlQE0kxrYdojlplW9Ox6nZqKOpeOW0cu6kbLPK@uswNrBRIBl6N92OvN6tWryfF8g4d@xqxumI2AnPyYppKF4skNBtBF39D6HaV3FapiaWJcsipptDTpMZ70RhI06vN5oBv11i3dqDkWrfru7W6a3QFnRuUVMC5A1@rW6fGV8irgncMAuWPwtQf3aYd@LW7nZO7c2dKco6lmQPHwkMVJMI8PbnwTy3yk4fpCDqI8Mo8t@lbmQr2yPFTeySV6Vr/nc09d8SskepIT1BryT27nP4bhV4sNGtVNJvNXw Try it online!]</span> I'm somewhat inclined to let it stand. --[[User:Thundergnat|Thundergnat]] ([[User talk:Thundergnat|talk]]) 13:22, 19 August 2019 (UTC)

:::::: I assume most visitors to this task page have noticed that there are no "BASIC" (interpretive) programming languages entered   This task (I think) shouldn't be about writing a very robust   '''isPrime'''   function (if a language doesn't have one),   but about (I assume) generating Pierpont primes.   Finding the 250<sup>th</sup> Pierpont prime (for each type),   is just a bridge too far.   So far,   at the time of this posting,   there are nine computer programming languages that accomplish the task's 4<sup>th</sup> requirement,   and I doubt there will be that many more   (perhaps there will be others entered when this draft task gets promoted   --- I've noticed that there's a surge of additional entries/solutions when a task gets promoted).   If the goal is to have as many computer programming languages entered for this task (for comparisons and learning),   this isn't the way to encourage that.   The Rosetta Code task   [https://rosettacode.org/wiki/Sequence_of_primorial_primes <u>sequence of primorial primes</u>]   has a similar problem,   but it does have more solutions/entries, however.     -- [[User:Gerard Schildberger|Gerard Schildberger]] ([[User talk:Gerard Schildberger|talk]]) 00:20, 25 September 2019 (UTC)

::::::: I rather suspect that the larger restriction for many Basics is (lack of, or not built in) large integer support rather than primality testing. (And even more than that, the lack of anyone with the urge to write an entry...) As I demonstrated above, Miller-Rabin is more than adequate to do the testing, and helpfully, there are many implementations in many different languages [[Miller–Rabin_primality_test|already available]]. If that doesn't float your boat, Pierpont numbers specifically lend themselves to primality testing by Proths theorem. The task is only asking for the 250th prime. There are other tasks asking for the 100000th prime; Cuban primes for example. If you don't want to do the task, or think it is too difficult, don't do it. It has already been demonstrated that the stated goals are pretty easily achievable.  --[[User:Thundergnat|Thundergnat]] ([[User talk:Thundergnat|talk]]) 12:01, 25 September 2019 (UTC)

:::::::: The Rosetta Code task Miller-Rabin primality test isn't that hard to code,   but it should be noted that the Rosetta Code M-R primality task was to write the code, it wasn't necessary to use the code and show examples, which some computer programming languages chose to do,   other entries/solutions used much smaller numbers to test, if at all.   Moreover, the 100,000<sup>th</sup> cuban prime   (by the way, isn't capitalized)   is only 13 decimal digits which can be easily tested for primality by trial division.   The 250<sup>th</sup> Pierpont prime (2<sup>nd</sup> kind) has 34 decimal digits.   Not exactly a good or fair comparison.   I concur that the stated goals are pretty easily achievable,   which is especially true if one is using an '''isPrime''' BIF.   I would like you to re-read the very first query on this page.   Clearly, it was a concern.   Just because a few (nine at this time) computer programming languages can perform primality checks for large numbers doesn't mean that other languages can find that goal obtainable   (testing for primality of 34 digit numbers).   This probably shouldn't/needn't be an issue that needs voting on.   Either it is or it ain't.   People also vote with their feet.     -- [[User:Gerard Schildberger|Gerard Schildberger]] ([[User talk:Gerard Schildberger|talk]]) 20:10, 25 September 2019 (UTC)

== Final Digits ==
Looking at the results, I see that there appear to be no Pierpont primes of the second kind ending with 9, but 9 is a relatively common final digit of the Pierpont numbers of the first kind. The distribution of the other possible final digits also appears to differ between them.
Maybe showing the numbers of each possible final digit would be interesting. Also, the First kind are clearly more frequent than the second kind. --[[User:Tigerofdarkness|Tigerofdarkness]] ([[User talk:Tigerofdarkness|talk]]) 09:48, 19 August 2019 (UTC)

::Though thinking about it, the first kind can never end in 1 and the second kind can vever end in 9... --[[User:Tigerofdarkness|Tigerofdarkness]] ([[User talk:Tigerofdarkness|talk]]) 11:32, 19 August 2019 (UTC)