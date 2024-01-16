FHS, Filesystem Hierarchy Standard
Defines the structure and layout, managed by Linux Foundation

#### bin
Binaries, programs

#### sbin
System binaries, for administrator

#### boot
Bootloaders

#### cdrom
Mounting point for cd-rom

#### dev
Devices
Everything is a file, devices are files
Example: Hard disk: `dev/sda`, Partition: `dev/sda1`, `dev/sda2`
Webcam, keyboard, drivers

#### etc
Etcetera
System wide applications configurations

#### home
Each user has its own folder

#### lib
|_ `lib`
|_ `lib32`
|_ `lib64`
Libraries - Files applications use

#### media
Mounted storage devices, leave this to OS to handle

#### mnt
Mounted storage devices, manually mounted
External USB drive, hard drives

#### opt
Optional
Manually installed software from vendors
Example: VirtualBox guest additions

#### proc
Pseudo files that contain information about system processes and resources
`cat /proc/cpuinfo`
`cat /proc/uptime`

#### root
`root` user's home folder

#### run
Is stored in RAM, used by processes that start early in the boot procedure to store runtime information that they use

#### srv
Service directory, stores service data

#### sys
System folder, interact with kernel, is created everything the system loads

#### tmp
Temporary directory

#### usr
User applications
`bin` is system level

#### var
Variable
Store files that are expected to grow in size
Example: Log files