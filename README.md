# A Kernel Seedling
count is a file in /proc and any time we cat into count, 
proc_count is called

To count the number of processes, I used for_each_process
to iterate through all the process in task_struct object and
printed the result using seq_printf

## Building
To build the module, I ran make
If I made changes, I would first run make clean the make

## Running
Loaded the module into the kernel using sudo insmod proc_count.ko
Then ran the file through cat /proc/count, which called proc_count
For me it produced the output of 139 follwed by a newline


## Cleaning Up
To remove build artifcats, I called make clean
Removed the module from kernel using sudo rmmod proc_count.ko


## Testing
Before testing, I have to make
Running python -m unittest produced 
...
-----------
Ran tests in 16.658s

okay

Report which kernel release version you tested your module on
(hint: use `uname`, check for options with `man uname`).
It should match release numbers as seen on https://www.kernel.org/.

-r : kernel release
-s: kernel name
-v: kernel version

Running uname -r -s -v produced
Linux 5.14.8-arch1-1 #1 SMP PREEMPT Sun, 26 Sep 2021 19:36:15 +0000