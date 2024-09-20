Virtualization
 
Dienyemite edited this page 2 hours ago · 3 revisions
Virtualization is the process of creating a virtual version of a system, such as hardware platforms, storage devices, and networks. It allows a single physical machine to run multiple operating systems (OSes) simultaneously by abstracting the hardware and resources. Let’s explore the three main types of virtualization—Full Virtualization, Paravirtualization, and Hardware-assisted Virtualization—with examples, graphs, and terminal snippets for each.

Full Virtualization Definition: Full virtualization provides a complete simulation of the underlying hardware, allowing an unmodified operating system to run in a virtual machine (VM) without modification. The guest OS is unaware it is being virtualized and interacts with virtual hardware as if it were the physical hardware.
How It Works: In full virtualization, the hypervisor (also known as a Virtual Machine Monitor or VMM) emulates all the underlying hardware. This means the guest OS thinks it is interacting with a full physical machine. The hypervisor translates the OS’s high-level requests into low-level instructions that the actual hardware understands.

Examples of Full Virtualization: VMware Workstation/Fusion/ESXi Microsoft Hyper-V Oracle VirtualBox Advantages: OS independence: The guest OS doesn’t need to know it’s virtualized. Easy migration: Since the OS doesn't need modification, VMs can easily move between different systems. Disadvantages: High overhead: Emulation of hardware can lead to a significant performance hit. Diagram: Here’s a basic diagram of full virtualization:

SQL

Copy code
Guest OS 1 (Unmodified)
--------------------------
Guest OS 2 (Unmodified)
--------------------------
Hypervisor (Full VMM)
--------------------------
Physical Hardware
--------------------------
Sample Terminal Commands (KVM/QEMU)
bash
Copy code
Installing KVM and QEMU for Full Virtualization (Ubuntu Example)
sudo apt update sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils virt-manager

Starting Virtual Machine
virt-manager # This opens a GUI to manage VMs using full virtualization 2. Paravirtualization Definition: In paravirtualization, the guest OS is aware of the fact that it is running in a virtualized environment. The OS is modified to interact directly with the hypervisor, which avoids the need to emulate hardware, resulting in better performance.

How It Works: The guest OS is aware of the hypervisor and has specific modifications that allow it to communicate directly with the hypervisor using special API calls, known as hypercalls. These hypercalls are much faster than the trapping and emulation techniques used in full virtualization.

Examples of Paravirtualization: Xen with PV Guests VMware ESXi (when used with VMware Tools) Advantages: Better performance than full virtualization since there's no need to emulate hardware. Reduced overhead due to efficient communication between guest and hypervisor. Disadvantages: The guest OS must be modified, which makes it more complex to manage and limits portability. Diagram: Here’s a diagram for paravirtualization:

lua

Copy code
Guest OS 1 (Modified)
--------------------------
Guest OS 2 (Modified)
--------------------------
Hypervisor (Paravirt.)
--------------------------
Physical Hardware
--------------------------
Sample Terminal Commands (Xen Hypervisor)
bash
Copy code
Installing Xen Hypervisor on Debian/Ubuntu
sudo apt-get update sudo apt-get install xen-hypervisor-amd64

Starting a Xen VM (paravirtualization mode)
xl create /etc/xen/config_file.cfg

Verifying the running VM
xl list 3. Hardware-assisted Virtualization Definition: Hardware-assisted virtualization uses CPU extensions to improve virtualization performance. Modern processors from Intel (Intel VT-x) and AMD (AMD-V) provide these extensions, allowing the hypervisor to offload some of the virtualization tasks to the hardware, minimizing overhead.

How It Works: With hardware-assisted virtualization, the hypervisor uses special CPU instructions (like Intel VT-x or AMD-V) that allow the guest OS to run at nearly native performance. The hardware provides efficient ways to handle context switches, privilege level changes, and memory management tasks that would otherwise have been handled by the hypervisor.

Examples of Hardware-assisted Virtualization: KVM (Kernel-based Virtual Machine) Microsoft Hyper-V (with Intel VT-x/AMD-V) VMware ESXi (with Intel VT-x/AMD-V) Advantages: Minimal overhead: Hardware extensions help achieve near-native performance. Unmodified guest OS: Like full virtualization, the guest OS does not need to be aware of the virtualization. Disadvantages: Requires modern hardware that supports CPU extensions. Diagram: Here’s a diagram for hardware-assisted virtualization:

lua

Copy code
Guest OS 1 (Unmodified)
--------------------------
Guest OS 2 (Unmodified)
--------------------------
Hypervisor
--------------------------
CPU Extensions (Intel VT)
--------------------------
Physical Hardware
--------------------------
Sample Terminal Commands (KVM with Hardware Extensions)
bash
Copy code
Verify if the CPU supports Intel VT or AMD-V
egrep -c '(vmx|svm)' /proc/cpuinfo

Installing KVM (Kernel-based Virtual Machine) on Ubuntu
sudo apt update sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils

Starting the VM using KVM
virt-manager # GUI to manage the VMs Graph: Virtualization Performance Comparison plaintext Copy code

Performance	Full Virtualization	Paravirtualization	Hardware-assisted Virtualization
CPU Overhead	High	Medium	Low
Memory Overhead	High	Medium	Low
IO Performance	Low	Medium	High
Conclusion:			
Full Virtualization provides complete abstraction of the underlying hardware but incurs a high performance overhead.			
Paravirtualization offers better performance by modifying the guest OS to interact directly with the hypervisor.			
Hardware-assisted Virtualization leverages modern CPU extensions to achieve near-native performance, reducing overhead while allowing unmodified OSes.			
Each type of virtualization has specific use cases, and the choice depends on the performance needs and the flexibility of the guest OS.		
