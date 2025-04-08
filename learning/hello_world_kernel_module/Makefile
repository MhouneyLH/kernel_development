# How to test what is working:
# See the kernel logs: sudo dmesg -W | grep Kernel
# Use the kernel module: sudo insmod hello.ko
# Remove the kernel module: sudo rmmod hello.ko

# all files will be built as kernel modules that are in obj-m
obj-m += hello.o

all:
	# look in the current directoy for additional module files
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) modules

clean:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) clean
