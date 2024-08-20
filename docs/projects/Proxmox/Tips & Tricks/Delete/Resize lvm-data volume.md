#### Remove and resize the default lvm-data volume
```sh
lvremove /dev/pve/data
```

#### Resize root partition
```sh
lvresize -l +100%FREE /dev/pve/root
```

#### Completing
```sh
resize2fs /dev/mapper/pve-root
```

#### Verification
```sh
lsblk
```