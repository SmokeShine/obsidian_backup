202510260003
Status: #idea
Tags:

# Docker

- We can copy folders from host
	- so, docker has a filesystem that makes it look there is one file system even though some may be from host and some may be from docker base image itself
	- this increases latency as check needs to be performed where the files are and what is the permission
		- this is happening with read only and writable  layers
	- For GPU training, this is costly
- Instead mount the file from host
	- this will be the data files, they are always mounted and not copied


---
# References

1. 