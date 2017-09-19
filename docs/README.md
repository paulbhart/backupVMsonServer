* Overview of HD structure
    * hartserver-vg (vg) 
        * basically OS / boot disk
        * HD
            * 20 GB SSD /dev/sdb
        * LVs
            * swap_1 50 GB
            * root 130 GB (ubuntu 16 /)
    * extra_space (vg)
        * basically space for active use 
            * VMs
            * Videos
        * Disks
            * 5 TB HD
            * LVs
                * playground 300GB (can be removed)
                * vmdisk 3T
    * backup (vg)
        * created using commands
            *  pvcreate /dev/sdc
            *  used gparted (graphical)
                * to create 1 primary ext4 partition (entire disk)
            *  sudo vgcreate backup_vg /dev/sdc1
        * place to hold any backups
            * VMs
            * base OS
            * disks
                * 5 TB single partition
            * lvs
                * important - size?