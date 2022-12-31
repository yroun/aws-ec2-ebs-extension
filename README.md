### aws-ec2-ebs-extension

```
$ lsblk
NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
xvda    202:0    0   60G  0 disk 
└─xvda1 202:1    0   60G  0 part /
```

```
$ sudo df -h /data
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       59G   53G  6.5G  89% /
```

```
sudo growpart /dev/xvda 1
```

```
$ lsblk
NAME    MAJ:MIN RM  SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  128G  0 disk 
└─xvda1 202:1    0  128G  0 part /
```

```
$ sudo df -h /data
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1      126G   53G   74G  42% /
```

```
$ sudo resize2fs /dev/xvda1
```

```
$ sudo df -h /data
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1      126G   53G   74G  42% /
```
