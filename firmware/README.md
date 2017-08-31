## Firmware insights

From: [avforums](https://www.avforums.com/threads/pan-ex85-faulty-tuner-now-u61-error.1452010/)

> HI everyone, I picked up a dmr-ex85s from a local recycling centre (£10) thinking that i could fix it with the help from the forum members, as i already have ex75 in a bedroom working great (£15.00) from a car boot sale. when i got the unit home and powered it up it started with a u61 error, i checked the forum and they suggested ram-drive head could be stuck/dirty , I cleaned the head and checked the movement, tried the machine again, still the same error u61. I read in The forum that the hd may be faulty. I tried a different hd (Seagate 160gb) but when I tried the hd in the ex85 the u61 error disappeared to be replaced with a hdderr, i reinstalled the old hard drive WD2500bb with a new cloned EX-85 boot loader (posted by a forum member) installed on it, but still hdderr so i tried a the Seagate 160gb hard drive with the (jumper set to cable select) with the cloned boot loader installed on it, (i was able to write the boot loaders using winhex on my pc and a usb drive caddy), It still had the same hdderr, so after checking on the forum the members said that i need a firmware update disc. I contacted Panasonic via email:

> dear, sir or madam, my trusted DMR-EX85 is experiencing colour fading/pulsing issue on the channel 4/Dave Ja Vu and one or two other channels). I searched on the internet and found that this is a common problem and that your company have released and firmware update disc "XY-322 (13/4/2010)" to fix my problem. Please could you send me a copy of this disc.

> Two weeks later my free copy arrived (i refused to pay £9.99 on ebay) i installed the disc (CD-R) but in only ran for 30 seconds showing that it was installing firmware and then spat out the xy-322 disc, only to find that the machine returned with a hdderr so i thought that the main ide controller board maybe faulty (where the hdd ide connector ribbon/foil fits to the pcb). So after a bit more head scratching and with nothing to loose I tried the 160gb Seagate again but this time I changed the jumper setting on the hd from cable select to master. I tried the machine again Bingo the machine started up but with a different boot sequence than previous, showing dvd in the front display, I put the firmware disc into the machine and after 6-8 minutes the machine sprung to life asking to format the hdd drive and now its working a treat.
I hope this post helps..

> JUST TO A RECAP

> 1. Yes you do need firmware disc XY-322 CD-R to format your hdd it is free from Panasonic,
> It is only 8.4mb file (PANA_DVD.FRM 21/07/2010)
> . You can use a different size drive as I did Seagate 160gb db35.
> 2 from a old sky box (cost me 50p)
> Set the new hd to master and NOT CABLE SELECT
> 3. My machine firmware is now version 1.20 (old version 1.16)
> Its a shame that Panasonic didn`t list this firmware on their website
> But you could buy it from eBay (copyright???)
> I think these are great machines, much better than my crappy old Philips dvd/hd recorder Thompson PVR

> Thanks john

From: [austech.info]( http://www.austech.info/showthread.php/53480-Panasonic-DVR-(DMR-EX75)-Service-manual)

> Hi Guys, unsurprisingly Ive had no feedback on such an old device, so when the opportunity arose I took the path of least resistance (aside from sending the EX75 to the recyclers).

> How I copied a working DMR-EX75 HDD to a replacement IDE drive (destination needs to be same size or larger than original, though by default the EX75 only "formats" to 160GB).

> Procured a 2nd hand Panasonic DMR-EX75 with a working Hard Disk - I'll call it the source (cheap because it couldn't tune DVB channels - my next project).

> Removed the HDD from the source EX75 and installed in my ancient but trusted firewire external drive enclosure.

> Experimented with Clonezilla on a HP Laptop until I found it didn't boot with firewire drivers. Doh! My USB enclosure was on loan to someone else so…

> Installed DiskArbitrator (from github dot com ) on my 2011 iMac running OSX 10.8.5. Started DiskArbitrator, enabled it and set it to "block mounts". Verified it worked as advertised by blocking writes to USB sticks & other firewire disks as I plugged them into the Mac. (DiskArbitrator in read only mode). That probably wasn't necessary, but I wanted to be doubly sure I wouldn't destroy the source disk before I'd extracted the boot code.

> Connected the firewire enclosure with the source HDD, and noted DiskArbitrator showed it connect as disk2.

> In the Mac Terminal window used dd to copy the first 200MB off the disk into a file. (From what I'd read elsewhere I think only 10MB is required, but it only took 2mins to read 200MB so why not?)
>        # mkdir EX75
>        # cd EX75
>        # dd bs=512 if=/dev/rdisk2 of=./EX75_HDD.dat count=409600
> where bs=512 sets the input & output block sizes o 512bytes, and doesn't aggregate short blocks,
> disk2 is the drive DiskArbitrator detected when I plugged in the firewire box,
> of tells dd where to create the 200MB "EX75_HDD.dat" file (on my Mac's internal disk, in the EX75 directory I created and changed directory to in the preceding lines),
> and 409600 is roughly 200MB.

> On completing the dd, leave the Terminal window open, don't shutdown the Mac. Took the source HDD offline from the Mac, de-activated but did not quit DiskArbitrator, swapped the destination HDD into the firewire enclosure, and turned it on.

> The Mac Finder saw the destination disk and asked if I wanted to format it, I said no. Noted that DiskArbitrator showed the destination disk as disk2.

> In the Mac Terminal window used dd to copy the file to the destination disk, only took 2mins:
>        # dd bs=512 if=./EX75_HDD.dat of=/dev/rdisk2

> Installed the destination disk in my destination EX75 and it booted successfully. I can't remember the details, but at some point the EX75 asked to "reformat" the HDD, I said yes.
