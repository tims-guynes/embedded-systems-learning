# embedded-phase1
## Phase 1 (Months 1–3): C, computer fundamentals, and the toolchain
### Goal: Think in C, understand what's happening at the memory/register level, and be comfortable in a terminal.

Goal - Understanding C and what happens at the memory/register level. BE COMFORTABLE AT IN THE TERMINAL
  * C language - focus on the following (Reading suggestion: C Programming: A Modern Approach; K. N. King [https://archive.org/details/c-programming-a-modern-approach-2nd-ed-c-89-c-99-king-by])
    1. pointers
    2. structs
    3. bitwise ops
    4. manual memory management
    5. the stack vs heap
    6. undefined behavior

  * Computer Architecture Basics (Reading Suggestion: But How Do It Know; J. Clark Scott [https://archive.org/details/jclarkscottbuthowdoitknowthebasicprinciplesofcomputersforeveryonejohnc.scott2009])
    1. How a CPU executes instructions
    2. what registers/memory-mapped I/O are
    3. binary/hex/two's complement
    4. endianess

  * Linux/CLI fluency
    1. bash
    2. file permissions
    3. processes
    4. make
   
  * Git (NON-NEGOTIABLE)
    1. branches
    2. commits
    3. resolving conflicts

# embedded-phase2
## Phase 2 (Months 3–6): Microcontrollers and bare-metal
### Goal: Move from "C on my laptop" to "C controlling real hardware," and understand registers well enough not to need HAL magic to feel safe.

Get an STM32 dev board (Nucleo boards are cheap, ~$15–25, and well-documented) plus a breadboard, LEDs, buttons, a logic analyzer or cheap oscilloscope later.
* Digital electronics fundamentals —
   1. Ohm's law (you've already done this),
   2. voltage/current/resistance,
   3. pull-up/pull-down resistors,
   4. debouncing,
   5. basic op-amp concepts. You don't need deep EE, just enough to not fry a board.
      
* Bare-metal STM32 programming —
   1. GPIO, without HAL first (direct register manipulation), then move to
   2. HAL/LL for productivity.
   3. Understand clocks, interrupts, timers, ADC, UART, SPI, I2C.
* Datasheets and reference manuals —
   1. learn to actually read them. This is a skill in itself; most beginners avoid it and stay stuck.
Resource: "Making Embedded Systems" (White), STM32 HAL examples, and ST's own reference manual for whichever chip you pick.

Deliverables (pick 3–4):

Blink an LED via direct register writes (no HAL) — proves you understand the hardware, not just a library call
UART echo/command console
PWM-driven servo or motor controller
I2C sensor reader (temperature/accelerometer) logging over UART

# embedded-phase3
Phase 3 (Months 6–9): RTOS, protocols, and debugging discipline

Goal: This is where you start looking like a hire-able engineer instead of a hobbyist.

 * RTOS concepts —
    1. tasks,
    2. scheduling,
    3. semaphores,
    4. mutexes,
    5. queues,
    6. priority inversion. Use FreeRTOS (free, ubiquitous, most job postings mention it).
       
 * Communication protocols —
    1. deepen SPI/I2C/UART,
    2. exposure to CAN (huge in automotive/industrial) or Modbus.
       
 * Debugging tools —
    1. JTAG/SWD debugging with a real debugger (not print statements),
    2. using GDB with OpenOCD,
    3. reading a logic analyzer trace,
    4. interpreting a hard fault / stack trace.
     
 * Version control discipline + code review habits —
    1. start writing code as if a senior engineer will read it: comments,
    2. consistent style,
    3. no magic numbers.

Deliverable: A multi-task FreeRTOS project — e.g., a sensor-logging system with one task sampling I2C sensors, one task handling UART command input, one task blinking a heartbeat LED, coordinated with queues/semaphores. This is a strong portfolio centerpiece.

# embedded-phase4
Phase 4 (Months 9–12): Specialization, polish, and the job search

Goal: Convert 9 months of skill-building into interviews and offers.

Pick a specialization lane based on job postings you're seeing locally/remotely: automotive (CAN, AUTOSAR-adjacent), IoT (low-power, wireless — BLE/LoRa), industrial/robotics, or medical devices. Don't specialize before month 9 — you don't yet know what you'll enjoy.
One capstone project that's portfolio-centerpiece quality: something with a custom PCB (KiCad — you mentioned this already), a real use case, and a README that documents the design decisions, not just "how to run it." This is what recruiters and hiring managers actually look at.
Interview prep:
C fundamentals whiteboard questions (pointers, memory, bit manipulation) — these come up constantly
Embedded-specific questions: volatile keyword, interrupt latency, memory-mapped I/O, RTOS priority inversion, stack overflow debugging
Practice explaining your projects out loud — this is often weaker than the technical skill itself
Resume + GitHub polish — pin your best 3 repos, each with a clear README, photos/videos of hardware running, and a one-paragraph "what this demonstrates."
Start applying at month 10, not month 12 — embedded hiring cycles are slow (weeks between stages), so you want applications in the pipeline before you're "done."
A few things that matter more than they seem
Your Flask/PostgreSQL background is an asset, not irrelevant — a lot of embedded roles increasingly want someone who can also write the backend/cloud side (IoT device fleets talking to servers). Don't hide that skill set in interviews.
Buy real hardware early. Simulators (like QEMU or online STM32 sims) are fine for concepts, but nothing replaces the experience of debugging a board that just... doesn't respond, and figuring out why.
Join a community — r/embedded, EEVblog forums, or a local makerspace. Embedded debugging often needs a second pair of eyes, and this also builds the network that gets you referred into roles.
Track everything in one GitHub org/profile from day one, even messy early code — hiring managers like seeing growth over time, not just a polished final product with no history.
