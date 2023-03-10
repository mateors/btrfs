# What is btrfs?
> Its a filesystem for storage device. Its more than just a filesystem.

## BTRFS Includes modern features

 * Protect your data
 * Its a "copy-on-write" filesystem

## Benefits of copy-on-writes?

 * Copies data rather than overwriting.
 * Benefits data integrity 
 * copy-on-writes features can be disabled
 * btrfs is the most advanced built-in filesystem
 * some distros use it by default



### Pros and Cons of btrfs

 * Pro:
	* snapshots are built-in
	* snapshots can help you revert to a previous state after testing something
	* subvolumes are very similar to paritiions
	* keeps track of size differently
	* so they are like partitions++
	* Checksums: helps ensure data integrity
	* protects against bitrot etc.

 * Cons:
	* How it implements raid
	* RAID is hit or miss
	* Built-in implementation of RAID
	* Don't use RAID in btrfs.
	* some features are unreliable

> Consult the status page for the latest info  on feature stability.
* https://btrfs.wiki.kernel.org/index.php/Status



## Demo time:

> sudo fdisk -l

> cat /etc/fstab

### What is subvolume?
A BTRFS subvolume is a part of filesystem with its own independent file/directory hierarchy and inode number namespace. Subvolumes can share file extents. A snapshot is also subvolume, but with a given initial content of the original subvolume. A subvolume has always inode number 256.

> subvolume treated as a partition + even more

> lsblk

> sudo blkid /dev/nameofthedevice

> sudo btrfs filesystem usage /

> sudo btrfs filesystem usage /home

### Quotas

> sudo btrfs

### Snapshots

> sudo btrfs subvolume snapshot /home /home/mystorageloc

> sudo btrfs subvolume list /home

> sudo cp /etc/fstab  /etc/fstab.bak


> sudo nano /etc/fstab

> reboot 


> sudo btrfs subvolume list /home

> which btrfs

> lsblk

> mkfs.btrfs /dev/sda 

> mkdir /mnt/btrfs-data

> mount /dev/sda /mnt/btrfs-data

> df -h

> sudo btrfs subvolume create /mnt/btrfs-data/myvol-1

> echo $?

> sudo btrfs subvolume list /mnt/btrfs-data


### How much storage used or available?

> sudo btrfs filesystem df /mnt/btrfs-data

> nano /mnt/btrfs-data/myvol-1/exmfile.txt

> ls -l /mnt/btrfs-data/myvol-1

> btrfs subvolume snapshot /mnt/btrfs-data/myvol-1 /mnt/btrfs-data/myvol-1-snapshot

> btrfs subvolume list /mnt/btrfs-data

> ls -l /mnt/btrfs-data/


## Learning Resource
* https://docs.kernel.org/filesystems/btrfs.html#:~:text=Btrfs%20is%20a%20copy%20on,open%20for%20contribution%20from%20anyone.
* https://christitus.com/btrfs-guide/
* [Modernize your Linux Storage with btrfs!](https://www.youtube.com/watch?v=RPO-fS6HQbY)
* [BTRFS Guide | The Best Desktop File System](https://www.youtube.com/watch?v=J2QP4onqJKI)
