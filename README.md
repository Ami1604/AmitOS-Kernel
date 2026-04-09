# AmitOS-Kernel
This as an operating system kernel project.
AmitOS-Kernel
An Educational Monolithic Kernel for x86 Architecture

📌 Project Overview
AmitOS is a 32-bit monolithic kernel developed as part of a 5-week Design Challenge. It demonstrates the fundamental principles of operating system design, including the transition from Real Mode to Protected Mode, GDT configuration, and basic hardware abstraction.

📄 Final Technical Report
The complete research paper and documentation are available here * [📄 View the Final Technical Report](./AmitOS-Kernel_Report.pdf). It covers the literature review, implementation methodology, and testing results.



🚀 Key Technical Features
Boot Sequence: Multiboot compliant boot.s handling the stack and GDT loading.

VGA Driver: Low-level memory mapping at 0xB8000 for color text output.

Keyboard Handling: Polling-based PS/2 controller driver.

Build System: Professional Makefile for automated compilation using the i686-elf-gcc cross-compiler.

🛠️ How to Run
To test AmitOS in a WSL/Ubuntu environment:

Compile: Run make to generate kernel.bin.
# 1. Assemble
as --32 boot.s -o boot.o

# 2. Compile
gcc -m32 -c kernel.c -o kernel.o -ffreestanding -O2 -Wall -Wextra -fno-stack-protector

# 3. Link (The crucial flags: -no-pie and --build-id=none)
gcc -m32 -T linker.ld -o myos.bin -ffreestanding -O2 -nostdlib boot.o kernel.o -lgcc -no-pie -Wl,--build-id=none,--no-warn-rwx-segments

# 4. Run
qemu-system-i386 -kernel myos.bin
👥 Contributors
Amit Gupta

Amit Verma

Shivani Yadav
