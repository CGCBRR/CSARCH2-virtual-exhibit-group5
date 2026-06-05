# CpU Later

## Group Members

- Barreo, Carlo Gabriel
- Eleydo, Renzel Vince
- Gregorio, Gaibril Kyle
- Leano, Jeremy
- Rebudiao, Daniel Christian

---

# Topic Theme

**How a CPU Works — Core Architecture, Instruction Cycle, Pipelining & Performance Optimization, and Caching**

---

# The Core Concept: How a CPU Works

At the absolute lowest level, the CPU acts like a speed computer that executes instructions provided by a computer program. A CPU is often referred to as the brain of a computer. It works by continuously moving data fetched from memory and sending it through the Control Unit where it is decoded.

An internal clock, operating at billions of cycles per second (GHz), coordinates the process. Once operations are complete, results are stored in memory as needed before the next instruction is fetched. This cycle repeats until all instructions are executed.

Each action is translated into binary commands (0s and 1s), which the CPU processes through the **Fetch–Decode–Execute Cycle**.

---

# Subtopics

## CPU Core Architecture

### Control Unit (CU)

The brain of the CPU. It handles data flow and directs the CPU's internal components and hardware.

### Arithmetic Logic Unit (ALU)

The engine room where all logical operations and mathematical calculations are performed.

### Registers

Fast temporary storage locations inside the CPU core.

#### Program Counter (PC)

Holds the memory address of the next instruction to be executed.

#### Accumulator (ACC)

The most frequently used register, storing data retrieved from memory and intermediate results.

#### Memory Address Register (MAR)

Holds the address of the memory location to be accessed. Works together with the Memory Data Register.

#### Memory Data Register (MDR)

Stores data being read from or written to memory.

#### Instruction Register (IR)

Holds the current instruction being executed.

### Internal Buses

Communication pathways that transfer data, signals, and memory addresses.

### Cache Memory

Fast memory located near the CPU that stores frequently used instructions and data.

### Floating Point Unit (FPU)

Handles floating-point operations, decimal calculations, and scientific computations efficiently.

---

# Instruction Cycle

## 1. Fetch Stage

The CPU retrieves an instruction from main memory (RAM). It uses the Program Counter (PC) to locate the address of the next instruction. The instruction is then loaded into the Instruction Register (IR), and the PC advances to the next instruction.

## 2. Decode Stage

The CPU determines what the instruction means. The Control Unit examines the opcode (operation type) and operands (data or memory locations), then prepares the CPU by issuing the required control signals.

## 3. Execute Stage

The CPU performs the instruction. This may involve arithmetic or logical operations in the ALU, moving data, or making control-flow decisions such as branching.

## 4. Memory Access

If required, the CPU reads data from or writes data to memory. This may involve retrieving values from RAM or storing results.

## 5. Write Back

The final result is written to a register or memory location. The CPU then proceeds to the next instruction.

---

# Pipelining and Performance Optimization

Pipelining is a technique that allows the CPU to process multiple instructions simultaneously by dividing instruction execution into stages.

### Pipeline Stages

1. **Instruction Fetch** – Retrieve instruction from memory.
2. **Instruction Decode** – Determine the operation to perform.
3. **Execute** – Perform arithmetic or logical operations.
4. **Memory Access** – Read or write data if required.
5. **Write Back** – Store the result in registers.

By overlapping these stages across multiple instructions, the CPU increases throughput and overall performance.

---

# Caching

Caching is a technique in which the CPU stores frequently used data and instructions in a small, extremely fast memory called the **cache**.

## How Caching Works

### 1. CPU Requests Data

The CPU requests a specific value or instruction.

### 2. Cache Lookup

The CPU checks the cache hierarchy:

- **L1 Cache** (fastest)
- **L2 Cache**
- **L3 Cache**
- **RAM** (slowest)

If the requested data is found, a **cache hit** occurs and the data is returned quickly.

If not found, a **cache miss** occurs and the CPU continues searching in lower cache levels or RAM.

### 3. Load a Cache Line

If the data is not available in any cache level, the CPU fetches a **64-byte cache line** containing the requested address from the next memory level.

### 4. Store in Cache

The fetched cache line is placed into the cache so future accesses can be completed faster.

---

# Tech Stack Plan

## Proposed Interactive Element

### Fetch–Decode–Execute Cycle Simulator

A simple calculator that supports:

- Addition
- Subtraction
- Multiplication
- Division

### Visual CPU Components

- Program Counter (PC)
- Instruction Register (IR)
- Arithmetic Logic Unit (ALU)
- Accumulator (ACC)
- Memory

### Animation Flow

#### Fetch

Animated visualization showing information moving from Memory to the Instruction Register.

#### Decode

Instruction Register highlights or expands to visually show instruction decoding.

#### Execute

The ALU visually performs the selected operation.

#### Result

Accumulator updates with animated feedback showing the computed result.

---

# Technical Tech Stack

## Core Framework

Following the Astro Build template:

- Node.js
- Astro 6
- React.js

## UI, Layout, and Animation Libraries

- Tailwind CSS (Styling)
- Shadcn/UI (Components)
- Framer Motion (Animations and Transitions)

---

---

# III. Style Guide Snapshot & Proposed Design Layout

To ensure our virtual exhibit is both visually striking and cognitively optimized for learning, we have established a concise, **mobile-responsive** design system. Our design language utilizes **"Cyber-Physical Glassmorphism,"** blending the aesthetics of raw machine hardware with semi-transparent digital interfaces to deeply immerse the visitor.

### 1. Design System Tokens & Psychology

* **Base Background:** Deep Silicon (`bg-slate-950`) – A dark-mode foundation featuring an ambient grid backdrop and blurred cyan glows to minimize eye strain and allow interface borders to pop.
* **Action Accent:** Bioluminescent Cyan (`text-cyan-400`, `bg-cyan-500/10`) – A high-energy color used exclusively to draw attention to interactive elements, execution traces, and active CPU stages.
* **Data Highlight:** Warning Amber (`text-amber-400`, `bg-amber-500/10`) – Used specifically to track data moving through the Instruction Register (IR) and Accumulator (ACC) during the Fetch-Decode-Execute flow.
* **Glass Containers:** Semi-transparent cards (`bg-white/5`) with a background blur (`backdrop-blur-md`) and subtle borders (`border-white/10`) to create structural depth.

### 2. Typography

* **Headers & Body Content:** *Geist Sans* – A highly optimized sans-serif typeface, establishing a clear visual hierarchy and perfect legibility inside dense instructional text blocks.
* **Simulator Data:** *Geist Mono* – Provides a realistic, machine-level data anchor for execution logs, opcodes, memory addresses, and component states.

### 3. Layout Architecture & Responsiveness

* **Progressive Disclosure:** Instead of overwhelming visitors with text walls, ShadcnUI Accordions are used to let users reveal complex content cards systematically (e.g., Core Architecture, Pipelining, Caching).
* **Micro-Interactions:** Active register blocks feature dynamic glowing drop-shadows (e.g., `shadow-[0_0_22px_-2px_rgba(34,211,238,0.55)]`) to provide immediate visual feedback during the execution cycle.
* **Mobile-Responsive Flow:** On mobile devices, the layout collapses into a vertical stack (`flex-col`), while desktop views utilize a precise 5/7 split grid (`md:grid-cols-12`). The calculator remains accessible while users simultaneously watch the CPU diagram update.



### Desktop Layout Snapshot

![Desktop View - Main](./image/README/PC%201.png)
![Desktop View - Footer](./image/README/PC%202%20FOOTER.png)

### Mobile Layout Snapshot

![Mobile View - Top](./image/README/MOBILE%201.png)
![Mobile View - Middle](./image/README/MOBILE%202.png)
![Mobile View - Bottom](./image/README/MOBILE%203.png)


# References

1. Badescu, R. (2023, October 12). *Anatomy of a CPU*. Medium.com. Retrieved June 5, 2026, from https://medium.com/@razvanbadescu/anatomy-of-a-cpu-bc02cd950cca
2. GeeksforGeeks. (2025, November 10). *Basics of Pipelining*. https://www.geeksforgeeks.org/computer-organization-architecture/basics-of-pipelining/
3. GeeksforGeeks. (2021, June 2). *Cache Memory*. https://www.geeksforgeeks.org/computer-science-fundamentals/cache-memory/
4. GeeksforGeeks. (2025, July 12). *Different Classes of CPU Registers*. https://www.geeksforgeeks.org/computer-organization-architecture/different-classes-of-cpu-registers/
5. GeeksforGeeks. (2018, March 29). *Computer Organization | Different Instruction Cycles*. https://www.geeksforgeeks.org/computer-organization-architecture/different-instruction-cycles/
