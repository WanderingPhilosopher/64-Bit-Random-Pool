# 64-Bit-Random-Pool
Two programs for joining the 64 bit random pool, part of the BTC challenge.


Ok. We have added a random pool in search of the #64 BTC challenge...in search of .64 bitcoin.
Join or view the discord channel here: https://discord.com/channels/871109371805962240/873949735185178694
and the server here: https://discord.com/channels/871109371805962240/871109507776921632

Updates and info will be given out on discord, not here.

How is this pool different than TDs 64 bit pool?
TD has a great pool. The entire 64 bit range is broken up into 2^27 ranges, each range is 2^36 bits in size.
Users help search and complete each range in its entirety. Meaning once connect to the pool and run your rig,
you have to search a complete 2^36 bit sized range. The idea is a 100% key by key search. Hopefully the key
is found before reaching the 50% mark.

This pool is different. I have broken the entire 64 bit range into 2^44 ranges. Larger ranges than the above,
but we will NOT be searching every key sequentially. Once connected to the pool, you will be assigned a range.
Your GPU will generate random points throughout the range and then start searching for the private key in that
range. Once started, your GPU will check x amount of keys or run for x amount of time. I have it currently set
up the maximum amount of time a single GPU will be in a range is 30 seconds. So your GPU gets assigned a range,
jumps in the range and generates random starting points, starts searching, runs for x amount of keys or 30 seconds,
whichever happens sooner. This way we are going in and out of ranges and at least searching in every possible range
within a limited time frame.

Depending on how many people/GPUs join the pool, we will search in every possible range in x days.
Example:
if we have 100 GPUs running 24/7
each GPU would check 2,880 ranges a day [1,440 minutes in a day, 2 ranges per minute (1 range every
30 seconds)]
2^19 ranges divided by 288,000 (100 GPUs x 2,880 ranges per day) = 1.82 days
every 1.82 days we will have searched every possible range
if we have 200 GPUs running 24/7 = every .91 day we will have searched every possible range

Example of ranges:
8000000000000000
80000FFFFFFFFFFF

8000100000000000
80001FFFFFFFFFFF

8000200000000000
80002FFFFFFFFFFF

all the way to

FFFFF00000000000
FFFFFFFFFFFFFFFF

How can you join?

Download the 2 files (here) or (here github).
Place them in the same folder.
Create a batch file such as:

Client.exe -d 0 -name username

If you have multiple GPUs on a single PC/rig, use the -d flag to signify which GPU to use. -d 0 for GPU 0, -d 1 for GPU 1, etc.

Replace the -name username with your actual username, such as for me, -name wanderph
I wanted to be able to use a BTC address but the database is case insensitive and at this time, that won't work
But please only use one username whether you have 1 GPU or 1,000 GPUs. Keep the username the same.
Example if using two GPUs:
GPU 0 = Client.exe -d 0 -name wanderph
GPU 1 = Client.exe -d 1 -name wanderph

If you have multiple GPUs, it is better to run each one on a separate/different instance versus running them together. If you
have 2 GPUs, let them run the program seperately, it helps the pool check each range quicker and gives you credit for 2 ranges 
versus 1 range.

The username is how the program tracks how many ranges you have been assigned and completed. This is IMPORTANT because this is
how we know who to pay and how much to pay them.
Users will be paid based on their work. Your total ranges checked divided by total ranges checked equals your payout.
Example:
You checked 125,000 ranges and it took us 1,000,000 ranges checked to find the key then your amount would be
125,000 divided by 1,000,000 = .125 percent of ranges checked. Now multiply that by the amount of BTC we will find, .60
so your BTC payout would be .125 multiplied by .60 = .075 BTC.

Wait, what? .60 ????? I thought it was for .64 BTC???? I am glad you are paying attention! .04 will go to the user who
finds the private key. Yes, the program allows me to see who actually found the key. So overall, the pool will split, based on
amount of work each user does, .60 BTC and the private key finder will get .04, in addition to their equal share. So if user
is owed .055 BTC based on their work, and they find the key, they will get .055 + .04 = .095 BTC. So make sure you run your
GPUs as often as you can. 

While we are searching for the key, you can message me your BTC address so I will have a record of it when we do find the key!
Once we find the key, I will message everyone who participated and sent me their BTC address to verify the address is correct.

And that's pretty much it. The who why when what.

The idea is if we visit every range every 1-2 days, the odds of us finding the key will be increased versus searching every range,
key by key. TDs pool has been operational for some time, and it's like any type of pool, it depends on how much hashing power
is pointed at it that determines progress. That pool has 134,217,728 ranges to search through and they are a little over 10% completed.
Where as this pool will be in the actual range the private key lies in, every x amount of days, depending on hashing power pointed at
the pool.

For now, this is just open to Windows users with Nvidia GPUs. Once I can figure out/precompile for Linux users, I will post.

I am sure I will add to or edit this as things change.

I have ran 2 days of tests with the server and client program without a hitch, but that was with limited GPUs running. So if 
some glitch does occur, bare with me and I'll get it fixed.

Kudos go to:
Jean Luc Pons and Telariust for original and modded Vanity Search.
I modded their work to create random points in specific ranges, each and every time.
Etar / Etayson for the client and server program groundwork.
I made a few tweaks to his program but really great work by him!
@dlystyr for his python experience and ability to write a python script in 3 seconds.
Also for his "ear", to listen to some of my crazier ideas regarding this BTC challenge.
@yoyodapro for his motivation and for setting up this channel to bring us all together.
and @bigvito for hitting me up every few weeks to work on the random feature until I finally
said dang, alright lol! But I got the idea while building him out a random version.

Stay tuned to the channel for imporant updates.

WP
