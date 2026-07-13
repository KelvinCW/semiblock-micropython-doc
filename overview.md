![overview banner](overview/overview.png){width=100% border="10px solid pink"}

## 1. Product Introduction

Semiblock.ai is a "Hybrid Visual-Textual" collaborative development platform specifically designed for low-level hardware development, embedded systems, and edge AI deployment. The core philosophy of the platform is to break through the steep learning curve of pure text-based coding and the performance bottlenecks of pure visual programming (block-coding). It allows developers to seamlessly switch between high-level logic diagrams and low-level hardware code within the same workspace.

## 2. Core Technology & Architecture

Semiblock.ai utilizes a bidirectional rendering engine and integrates cutting-edge AI code generation models, focusing specifically on the development experience for hardware logic and microcontrollers:

- Hybrid Logic Canvas: Allows developers to build system architectures and state machines by dragging and dropping "Blocks." Every block can be "unfolded" into underlying code (such as C, C++, Verilog, or Assembly) at any time for deep fine-tuning.

- AI Hardware-Aware Synthesis: Features built-in AI models optimized specifically for hardware. It automatically analyzes underlying logic, provides real-time code completion, offers timing optimization suggestions, and assists in troubleshooting memory synchronization issues.

## 3. Key Functional Modules

3.1 Embedded Systems & Microcontroller Workspace (MCU Workspace)
Provides an out-of-the-box development environment for various microcontrollers, eliminating tedious register configuration:

- AVR & PIC18 Support: Configure GPIO, interrupts, and timers through a visual interface, automatically generating optimized AVR Assembly or C code.

- STM32 Logic Block Mapping: Natively supports STM32 programmable logic blocks (PLAY/CLB), allowing direct generation of corresponding configuration code by dragging logic gate diagrams.

3.2 FPGA & SoC Hardware Acceleration Pipeline (Hardware Logic Pipeline)
A dedicated toolchain built for the pain points of custom hardware logic development:

- Visual AXI Interface Configuration: Simplifies the handshake protocol for Master/Slave AXI interfaces. The platform automatically generates standard-compliant Verilog templates.

- Native Zynq 7020 Adaptation: Provides PS (Processing System) and PL (Programmable Logic) interactive synergy templates specifically for the Xilinx Zynq 7020 development board, enabling one-click bitstream compilation and programming path configuration.

3.3 Edge AI & Compute Cluster Integration (AI & Compute Hub)
Provides seamless integration for high-compute demands and local AI deployment:

- Local LLM Deployment: Offers one-click tools to quantize and package open-source models like Qwen, optimizing their execution efficiency on Mac M5 architectures and edge devices.

- Distributed Compute Scheduling: Supports interfacing with DGX Spark clusters, allowing developers to directly allocate high-load computing tasks or model fine-tuning workloads from the platform.

## 4. Infrastructure & DevOps Integration
Semiblock.ai fully accommodates modern CI/CD workflows, supporting seamless integration with enterprise or private code repositories:

- Containerized Architecture Support: Provides dedicated Webhook and CI Runner configurations that deeply integrate with GitLab Community Edition (including the latest updates like 18.8.x) running in Docker environments, enabling automated hardware simulation and testing after code commits.

- Modular Version Control: Whether it is a change to a visual Block or a modification to the underlying Verilog, the platform universally converts them into standardized Git commits, facilitating team collaboration and code tracking.

## 5. Applicable Scenarios

- Rapid Prototyping: Ideal for part-time programmers or independent developers who need to verify low-level hardware logic in a very short amount of time.

- Education & Research: Serves as an advanced supplementary tool for IT and engineering disciplines, helping students intuitively understand complex hardware state machines and underlying microcontroller principles.

- Extreme Environment Equipment R&D: Highly useful in the development of mission-critical systems (such as the pressure control systems or communication modules of deep-sea exploration drones), leveraging its rigorous logic verification and AI timing checks to reduce error rates.
