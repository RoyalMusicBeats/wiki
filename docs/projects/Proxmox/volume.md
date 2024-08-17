##remove volume

1. Remove /dev/pve/data
lvremove /dev/pve/data

3. Resize root partition
lvresize -l +100%FREE /dev/pve/root

5. Completing
resize2fs /dev/mapper/pve-root

7. Verification
lsblk
