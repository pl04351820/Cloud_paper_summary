## Linux Kernel

### Memory allocation 
The problem is more like assign memory block more efficiently. Fisrt-fit strategy / Best-fit / Buddy Memory Allocation.

#### buddy system 
Implement it by using a perfect tree. Setbits and clearbits API to set the block area continuously.

#### virtual page 
Linux use three-level page table to see the address translation.
TLB 
Fork state -> Share common page first than COW state. (COW is also used in docker aufs)

#### page memory 
User Space: Heap / Stack / BSS / Data / Text 
Kernel Space: 

#### mmap
mmap(): map the memory space to kernel space. Hence, the change of user space can be kernel space directly.
Traditional Unix filesystem in user space, multi thread need to create their own file in its stack, so multiple threads will open one file multiple times. Shared memory is used to solve this problem. (mmap system call) 

#### kmalloc / vmalloc
kmalloc guaranteed to get contiguous physical blocks of memory. (PCIe DMA access)
vmalloc needs to relocate the space into different areas.

#### Linux slab 
Memory pool cache for linux system. 
Kernel memory allocation is more focused on small object. These small objects will reallocate many times in their life cycle. To avoid fragement problem. Slab use cache strategy to avoid it.

#### memset 
Used to initilize the memory address.