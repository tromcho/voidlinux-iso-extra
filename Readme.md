# voidlinux-iso-extra

This is almost official ISO for [Void](https://voidlinux.org/) (Linux). It has few additional packages that I find essential but are missing in official ISO.

This repo contains instruction for building it yourself and link to generated ISO.

## Download ISO

* [https://github.com/kotoko/voidlinux-iso-extra/releases/download/2020-07-02/void-live-x86_64-5.4.49_1-20200702.iso](https://github.com/kotoko/voidlinux-iso-extra/releases/download/2020-07-02/void-live-x86_64-5.4.49_1-20200702.iso)
* [https://www.dropbox.com/s/uspcf1rijxbhyre/void-live-x86_64-5.4.49_1-20200702.iso?dl=1](https://www.dropbox.com/s/uspcf1rijxbhyre/void-live-x86_64-5.4.49_1-20200702.iso?dl=1)

## Regenerating ISO

Internet is required for your system and also for Void inside VirtualBox.

1. Install VirtualBox.
2. Download latest minimal ISO for x86_64 from official website [https://alpha.de.repo.voidlinux.org/live/current/](https://alpha.de.repo.voidlinux.org/live/current/) (e.g. `void-live-x86_64-20191109.iso`).
3. Add new system to VirtualBox.
    * Create 4GB virtual disk hard drive.
    * Add more RAM (2-4 GB should be OK).
    * Add more CPU (2 is already better)
4. Install Voidlinux in virtualbox.
    * Run Voidlinux from RAM (will be faster).
    * Login as `root`.
    * Run `void-installer`.
    * Choose local installation (not network installation).
    * Create one partition for `/`.
    * After installation reboot into new system (not livecd again).
5. Login as `root`.
6. Copy `gen.sh` into any ssh server.
7. Use scp to download `gen.sh` into `/root/` in Voidlinux inside virtualbox. (E.g. `scp me@myserver:gen.sh /root`)
8. Run script: `bash /root/gen.sh`
9. New ISO will be in folder `/root/void-mklive/`. Use scp to copy it outside VirtualBox.

Done!
