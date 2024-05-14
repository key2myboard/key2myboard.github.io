---
layout: post
title: How to Fix ‘Enter a password to unlock the disk “Macintosh HD - Data”’ Prompt
subtitle:
gh-repo: key2myboard.github.io
gh-badge: [star, fork, follow]
tags: [macOS]
comments: true
---

Recently it came to my attention that my MacBook, which I received secondhand, still had a volume that belonged to its previous user. Each time I turned my laptop on and logged in, I would receive a message prompt asking that I enter the password to the the user’s Macintosh HD - Data volume in order to unlock it.

[image]

I did some investigating and here's what I found that helped me resolve this persistent error message.

## What is Macintosh HD - Data?
Some macOS versions use two volumes to store data: the System volume (Macintosh HD) which contains the macOS itself along with system-level files, and the Data volume (Macintosh HD - Data) that contains user-specific data such as documents, desktop files, apps and more.

Essentially, system files are stored in the Macintosh HD volume and user files in the Macintosh HD - Data volume as part of Apples separation strategy. These two volumes are linked together in a volume group.

To see this I you can visit Disk Utility on your mac in the Utilities folder in your Applications folder:

1. Open Finder
2. On the left panel select “Applications”.
3. Scroll down to locate the “Utilities” folder, click to open.
4. Locate Disk Utility, click to open.

[image]

There you will be able to visualize the volumes hiarchy.

[image]

Here you notice the second Macintosh HD - Data greyed out. Also notice it’s not mounted.

## What was this volume doing on my laptop?
In my situation, there was an HD Data volume that remained on my mac from the previous owner that was mistakenly left behind when they attempted to clear it out for a new owner. I didn’t have access to the volume, as it was safely locked behind their login password, but it was taking up storage space.

[image]
See charted here the Other Volumes greyed out. Navigate from Apple logo > System Settings > General > Storage

## How to delete the unwanted volume

First, it’s important that you identify the volume you are looking to remove (even though you may not be able to delete the wrong one). Here’s how you can investigate to ensure you’re targeting the volume your intend to erase.

Check delete capability and mount point

Navigate to Disk Utility located in Finder > Applications > Utilities folder > Utility Disk.
On the left panel, as I pointed out above, you will see two "Macintosh HD - Data" volumes. One of which will likely be greyed out. Select that one, and check the Mount Point.

You may notice that the volume is “Not Mounted” while if you select the other Data volume, the Mount Point is "/System/Volumes/Data". You may also notice the when you right click on the volume, most altering menu options are greyed out as well. Meaning you cannot delete the volume.

Additionally, if you attempt to mount the volume, the **“Enter a password to unlock the disk ‘Macintosh HD - Data’” prompt pops up.**
Once you’ve identified to Data volume you wish to delete, right click on it and select “Delete APFS Volume…”

<!-- Include another way to ensure proper volume by compairing storage amount -->

[image]

The previous owner's data will be deleted, resolving the password prompt from popping up and freeing up your storage.

[image]
Storage space recovered.

## How to properly reset your Mac to prevent this issue

Now, I’m sure you’re curious to know how to properly reset a computer, and prevent this kind of issue. When you go to erase your Mac, you must ensure that you don’t just erase "Macintosh HD", and leave "Macintosh HD - Data" behind. 

To erase your Mac correctly, pay attention that when you select either "Macintosh HD" or "Macintosh HD - Data", click Erase, you then select “**Erase Volume Group**”. This erases and deletes the linked data volume, and then erases the system volume so that you can have a clean slate and then reinstall macOS.

More info here https://support.apple.com/en-us/HT201065
