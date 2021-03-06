## ZFS-Auto-Deploy
#### Joseph Sirianni
#### Version 0.3.1


### Supported OS
  - Ubuntu 16.04 w/ default kernel 4.4


### Prerequisites
  - Packages: sudo, python3
  - Root or sudo privileges


### Features
  - Interactive ZFS on Linux install
  - Supports several RAID configurations
    - Mirror VDEV (RAID 1)
    - RAIDZ1
    - RAIDZ2
    - RAIDZ3
  - Supports creation of multiple datasets
  - ZFS-Auto-Snapshots
    - Enable or disable top level snapshots (zpool and all datasets)
    - Enable or disable snapshots, for each dataset.
    - Frequent, Hourly, Daily, Weekly, Monthly snapshots.
  - Optional: Setup ZFS email alerts
  - Optional: Enable ZFS compression (LZ4 Only)



### Packages Installed
  - zfsutils-linux from Ubuntu repositories
  - uzip from Ubuntu repositories
  - zfs-auto-snapshots, from jsirianni/zfs-autosnapshot-packages
    - Source: zfsonlinux/zfs-auto-snapshot
  - msmtp and required dependencies


### How to install
  - `git clone https://github.com/jsirianni/zfs-auto-deploy.git`
  - `cd zfs-auto-deploy`
  - `chmod +x install.py`
  - If email alerts are desired, edit zed.rc
    - Configure 'ZED_EMAIL_ADDRESS'.
    - Set to the address that will receive ZFS alerts.
  - `sudo ./install.py`
  - Follow the prompts


### Things to note
  - Setup will prompt for a sending email-address/password.
    - This email is what the system uses to SEND alerts.
    - You should use a throw away email because the password is stored in plain text!!!
      - It is important to note that the email specified in zed.rc can be a real email address, as it is the recipient.

  - Striped VDEVs (RAID0, RAID10) will be supported in a later release.
  - LZ4 compression is used by default. Other compression options will be available in a later release.
