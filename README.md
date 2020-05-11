cloned from https://github.com/diskfs/go-diskfs

purpose: test if it supports ext3/ext4.

with an image that has fat32 file system, things work fine:
Take a look at the test func TestRead, which reads an image with fat32 file system

# ➜  go-diskfs git:(master) go test diskfs_test.go   
ok  	command-line-arguments	0.066s

However, if we switch the image to a ubuntu image, http://cloud-images.ubuntu.com/minimal/releases/disco/release-20190417/ubuntu-19.04-minimal-cloudimg-amd64.img, the test failed.
This means it does not apply to ubuntu image. 
It does not help if we try to read file system from a different partition (via disk.GetPartitionTable()). 

