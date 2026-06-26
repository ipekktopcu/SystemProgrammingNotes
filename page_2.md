### WSL / Windows & Linux Cross-Copying
When using WSL, Windows drives are mapped under `/mnt/`:
* `/mnt/c/Users/Ipek/Downloads`
* `/mnt/c/Users/Ipek/Desktop/proje`

* Windows and WSL have different IP addresses because they are treated as separate network entities with their own interfaces (uses NAT internally).

### Operating System Kernel Types
* **Monolithic (Linux):** Everything runs in kernel space (fast but large).
* **Microkernel (Chorus, Mach):** Moves as much as possible out of the kernel into user space.
* **Hybrid:** (Windows NT)
* **Layered:** (THE)
* **Exokernel:** (MIT)

### CPU Architecture: Exceptions vs. Interrupts
* **Exceptions (Internal / Synchronous):** Occur within the CPU. Caused by the instruction currently running (e.g., Error / Divide by Zero like `div reg1, reg2`).
* **Interrupts (External / Asynchronous):** Generated outside the CPU by hardware components to ask for attention from the CPU (e.g., Keyboard input, network traffic).

#### Hardware Interrupt Flow:
H/W Device -> Sends Interrupt Signal -> CPU stops current task -> Kernel Interrupt Handler fetches next task/slice

