# How to test what is working:
# See the kernel logs: sudo dmesg -W | grep Kernel
# Use the kernel module: sudo insmod hello.ko
# Remove the kernel module: sudo rmmod hello.ko

# all files will be built as kernel modules that are in obj-m
obj-m := hello.o

KDIR := /lib/modules/$(shell uname -r)/build
BUILD_DIR := $(PWD)/module

all:
	mkdir -p $(BUILD_DIR)
	make -C $(KDIR) M=$(PWD) modules

	# move all generated files away from source
	mv *.ko *.o *mod* Mod* .*.cmd $(BUILD_DIR)

clean:
	make -C $(KDIR) M=$(PWD) clean
	rm -rf $(BUILD_DIR)