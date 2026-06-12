CSARCH2 Virtual Exhibit: Case Study Proposal

Group Title: Ca-Ching! (Group 5)
GitHub Repository Link: https://github.com/CGCBRR/CSARCH2-virtual-exhibit-group5

Group Members:
Barreo, Carlo Gabriel
Eleydo, Renzel Vince
Gregorio, Gaibril Kyle
Leano, Jeremy
Rebudiao, Daniel Christian

Topic Theme: Caching! - How Cache Memory Works?

I. The Core Concept: How Cache Memory Works

1. The Hardware Speed Gap and Cache Memory
The Hardware Speed Gap: CPUs have become incredibly fast, while the main memory (RAM) has remained fairly slow. Even though RAM is more affordable, the speed is its drawback. This creates a severe problem where a fast processor constantly wastes time waiting for data from the slower RAM. This is where Cache Memory kicks in.

Cache Memory: A small, ultra-fast memory that sits directly or next to the CPU. It bridges the gap between RAMs and CPUs by acting as an ultra-fast buffer that frequently stores used data. It also serves as a temporary storage area from which the computer's processor can efficiently retrieve data. Cache memory operates approximately 10 to 100 times faster than random access memory (RAM) and typically responds to a central processing unit (CPU) request within a few nanoseconds.

2. Cache Hits vs. Cache Misses
A cache hit happens when the CPU requests data and finds it already stored in the cache memory. Since cache is much faster than RAM, the CPU can retrieve the data quickly without waiting for slower memory access. This makes the computer run faster because the processor spends less time searching for information.

A cache miss happens when the CPU requests data but cannot find it in the cache. The CPU then has to check other memory such as L2, L3 cache, or RAM to get the data. Since these memory levels are slower than the cache, it takes more time and can slow down the computer.

How Cache Hits and Cache Misses Work:
CPU requests data: The processor first checks the cache memory.
Cache lookup: If the requested data exists in the cache, a cache hit occurs and the CPU immediately uses the data.
Cache miss: If the data is unavailable, the CPU searches lower memory levels until the data is found.
Cache update: After retrieving missing data, the CPU stores a copy inside the cache so future requests can be faster.

3. Principle of Locality in Cache of Reference
The Principle of Locality refers to the idea that programs tend to use the same data and instructions repeatedly or access the data that is located near recently accessed data. When applied in caching, this improves its effectiveness in fetching data. Ideally, there are two main types of locality:

Temporal Locality (Locality in Time): In this principle, it basically says that if a memory location is accessed, it is likely that it will be accessed again soon. For example, a program that adds a value repeatedly:

for (int i = 0; i < 1000; i++) {
    sum += total;
}

Here, the variable total is accessed multiple times through each iteration, this means that keeping those variables in the cache allows for faster storing and fetching from the memory.

Spatial Locality (Locality in Space): Likewise, Spatial Locality says that if a memory location is accessed, it is likely that nearby memory locations are likely to be accessed soon also. For example, a program that adds all the values of an array together:

for (int i = 0; i < 1000; i++) {
    sum += arr[i];
}

In this program arr[i] is being traversed sequentially and since the array elements are stored next to each other in the memory, loading one cache block often brings in nearby elements that will soon be needed.


II. Tech-Stack Plan

1. Proposed Interactive Element: CPU Cache Visualizer
Users can simulate requesting data from a specific hex address by typing it, simulating a CPU requesting data.

After the user types in the hex address, calculations are shown on the screen visually:
The system will convert the hex address to binary.
It will slice the bits (Tag, Index, Offset).
Lines or glowing particle streams shoot out from each sliced section to show exactly where they go in the cache hardware.

Cache Hit Visualization:
The system checks the calculated row index, sees the valid bit is active, and confirms the address tag matches the stored tag.
The targeted grid cell glows, isolates the data using the offset bits, and shoots a fast light color back to the CPU with low latency stats.

Cache Miss Visualization:
If the row is empty or the tags don't match, flashing a miss icon and sending a slow, sluggish gray data stream crawling down to RAM.
RAM fetches a full block of data to exploit spatial locality, overwrites the cache row's metadata, and finally sends the data back to the CPU with high latency stats.

2. Technical Tech Stack
To ensure seamless integration with the central virtual museum repository, our core framework will strictly utilize Node.js 26 and Astro 6, building directly upon the provided astro.build template.

For our interactive CPU Cache Visualizer we will develop the visualization logic using ReactJS components embedded within Astro's .mdx pages. To guarantee a highly mobile-responsive layout, we will use TailwindCSS for structural styling alongside ShadcnUI to provide clean, accessible interactive elements. Finally, to bring the cache visualizer to life, we will implement Framer Motion to handle the complex visual transitions, such as animating the calculations, and the data flowing from the cache to the CPU or memory to the CPU.


III. Style Guide Snapshot

To ensure our virtual exhibit is highly engaging and accessible, we will utilize a Cyber-Physical Glassmorphism design system built with Tailwind CSS and ShadcnUI. This layout is optimized for both desktop and mobile viewing and perfectly complements our Cache Memory simulation.

Color Palette: Deep dark mode background (slate-950) with high-contrast, glowing accents to indicate data flow between the CPU and memory hierarchy.
State Indicators: We will use vibrant green and cyan glowing borders to indicate Cache Hits, and muted gray and amber tones to indicate slower Cache Misses when the CPU has to fetch from main memory.
Typography: Clean, sans-serif fonts (such as Inter or Geist) for high readability in the educational Exhibit Notes accordion sections.
Layout Structure: A split-panel view on desktop (Interactive Simulator on the left, Cache Visualizer on the right) that seamlessly stacks into a single scrollable column on mobile devices using a responsive grid system.

Proposed Virtual Exhibit Design Layout:
(Below is the high-fidelity UI snapshot of our proposed Cache Memory Visualizer)

**1. Desktop View: Cache Hit State**
*(Below is the full UI showing a successful Cache Hit)*
<img width="1087" height="584" alt="1" src="https://github.com/user-attachments/assets/57dbc090-3085-4c76-8231-949b8ffdf5e4" />

**2. Desktop View: Cache Miss State**
*(Below is the full UI showing a slower Cache Miss fetching from RAM)*
<img width="1090" height="591" alt="2" src="https://github.com/user-attachments/assets/e7f01dcb-3829-4ba0-9e42-6d8deb498d4c" />

**3. Mobile View / Component Breakdown**
<img width="213" height="483" alt="4" src="https://github.com/user-attachments/assets/c3b68db1-1fbb-4d79-ac0a-f914ff03d050" />
<img width="218" height="506" alt="3" src="https://github.com/user-attachments/assets/2b2e8621-0582-470c-b738-3202daded6ff" />
<img width="238" height="510" alt="5" src="https://github.com/user-attachments/assets/f026b08a-2cb3-40fe-9447-b27e17972403" />
<img width="244" height="516" alt="6" src="https://github.com/user-attachments/assets/d1943d74-ce02-45e6-b1fa-78a275e96186" />




IV. References

Cache Miss vs Cache Hit: What’s the Difference? (2023, May 10). WP Rocket. https://wp-rocket.me/wordpress-cache/cache-miss-vs-cache-hit/
Lutkevich, B. (2024, June 25). cache memory. Search Storage. https://www.techtarget.com/searchstorage/definition/cache-memory
