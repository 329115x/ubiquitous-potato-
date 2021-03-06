Release Notes  -  SABnzbd 1.2.0
====================================

## What's new in 1.2.0
- New SSL engine:
  * SSL connections will always negotiate strongest encryption available
  * Strict verification of certificates (optional)
  * Set custom SSL-Ciphers to increase performance (lowers encryption strength)
  * Detail information in Status window on type of encryption used
  * Webserver can use stronger encryption for HTTPS connections
- New RAR-file processing with full support for RAR5:
  * All passwords are now tried on the first complete RAR-file during download
  * RAR-based verification when no par2-files or SFV-files are available
- Improvements to Categories processing:
  * Matching of start of category inside NZB with user-categories
    For example 'Movies > HD' will match a 'movies' category
  * Categories can now be ordered to customize matching to categories in NZB's
- Improvements to RSS feed management:
  * Multiple feeds can now share the same set of filters
  * Added 'From Show SxxEyy' filter
  * Feeds will only re-evaluate after clicking 'Apply Filters' or 'Read Feed'
  * Information from newznab, nZEDb and nntmux tags used (age, size and show info)
  * Feeds now show the category, age and when the NZB was added to the queue
- Detection of par2-files in completely obfuscated NZB's
- Verification (par2) and UnRAR can now be aborted from Glitter
- Faster startup and restart of SABnzbd
- Duplicates can now be marked as Failed (to notify external tools)
- Config Search function

## Changes:
- Python post/pre/notification-scripts now require execute (+x) permissions
- Dropped dependency on PyOpenSSL, now only requires cryptography package
- Update 7zip to 16.04 and UnRar to 5.40 for Windows/macOS
- Update Python to 2.7.13 on Windows and macOS binaries
- CherryPy logging only enabled when forced via command line
- Not having C yEnc module will trigger warning on startup

## Bug fixes
- Re-use IP-address for new connections when a server has open connections
- Auto-disables CPU-usage optimizations if they result in slowdown
- no_penalties now applies to all types of penalties
- par2cmdline would fail jobs in folders ending on ".par2"
- Fix problem where memory usage wasn't correctly limited, causing MemoryError's
- Removing files from active download was not working correctly
- Accept & fail for pre-queue script was not working correctly
- Recursive unpack failed on Windows with very long paths
- Problems loading Notifications page with Scripts Folder set

## Translations
- Many translations updated, thanks to our translators!

## About
  SABnzbd is an open-source cross-platform binary newsreader.
  It simplifies the process of downloading from Usenet dramatically,
  thanks to its web-based user interface and advanced
  built-in post-processing options that automatically verify, repair,
  extract and clean up posts downloaded from Usenet.

  (c) Copyright 2007-2017 by "The SABnzbd-team" \<team@sabnzbd.org\>

### IMPORTANT INFORMATION about release 1.x.x
<https://sabnzbd.org/wiki/new-features-and-changes>

### Known problems and solutions
- Read the file "ISSUES.txt"

### Upgrading from 0.7.x and older
- Finish queue
- Stop SABnzbd
- Install new version
- Start SABnzbd

The organization of the download queue is different from older versions.
1.x.x will not see the existing queue, but you can go to
Status->QueueRepair and "Repair" the old queue.
Also, your sabnzbd.ini file will be upgraded, making it
incompatible with releases older than 0.7.9
