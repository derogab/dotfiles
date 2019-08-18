# dotfiles/linux/disk-partitioning

Some info about my **disk-partitioning**.

### Laptop 

#### HD `/dev/sda`

| Partition 	| File System 	| Mounting Point 	| Size    	| Flag 	|
|-----------	|-------------	|----------------	|---------	|------	|
| /dev/sda1 	| linux-swap  	|                	| 6 GiB   	| swap 	|
| /dev/sda2 	| ext4        	| /              	| 460 GiB 	|      	|

#### SSD `/dev/sdb`

| Partition 	| File System 	| Mounting Point 	| Size   	| Flag      	|
|-----------	|-------------	|----------------	|--------	|-----------	|
| /dev/sdb1 	| fat32       	| /boot/efi      	| 300MiB 	| boot, esp 	|
| /dev/sdb2 	| ext4        	| /boot          	| 300MiB 	|           	|
| /dev/sdb3 	| ext4        	| /tmp           	| 4GiB   	|           	|
| /dev/sdb4 	| ext4        	| /opt           	| 18GiB  	|           	|

