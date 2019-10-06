# awsec2
Possibilities of recover at ec2 with problems of access SSH.

```
[  157.460961 ] XFS (xvdf1): Filesystem has duplicate UUID dd8f0afe-5a00-40ff-b538-5fa0a351cdba - can't mount

[root@ec2-reinaldo: /mnt]$ xfs_admin -U 00000000-0000-0000-0000-000000000123 /dev/xvdf1
Clearing log and setting UUID
writing all SBs
new UUID = 00000000-0000-0000-0000-000000000123

[root@ec2-reinaldo: /home/centos]$ mount /dev/xvdf1 /test/
[root@ec2-reinaldo: /home/centos]$ cd /test/
[root@ec2-reinaldo: /]$ ls
backup-20160316.sql  bin  boot  dev  etc  home  lib  lib64  media  mnt  opt  proc  root  run  sbin  srv  sys  test  tmp  usr  var
[root@ec2-reinaldo: /]$ umount /test/
[root@ec2-reinaldo: /]$ xfs_admin -U dd8f0afe-5a00-40ff-b538-5fa0a351cdba /dev/xvdf1
Clearing log and setting UUID
writing all SBs
new UUID = dd8f0afe-5a00-40ff-b538-5fa0a351cdba
```
