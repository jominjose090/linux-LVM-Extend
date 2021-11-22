# linux-LVM-Extend

**check the new disk using** 
```
fdisk -l
```
**create physical volume from newdisk**
   ```
   pvcreate /dev/newdisk
   ```

**check the volume group and replace in vggroupname in below commands.**
   ```
   vgs
    
   vgextend vggroupname /dev/newdisk
   ```

 **check the size again for the volume group**
   ```
   vgdisplay
   ```
   
 **check the logical volume name and replace in *lvname* in below commands to extend the lvm size to maximum available.**
   ```
   lvs
   lvextend -l +100%FREE lvname
   ```
 **expand the file system to adjust with the new change**
   ```
   resize2fs lvname
   ```
