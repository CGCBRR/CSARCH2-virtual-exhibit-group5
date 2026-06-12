# CSARCH2 Virtual Exhibit: Case Study Proposal

## 📝 Revisions Highlight (From Initial Submission)
To fully align with the project rubrics and feedback, our group has made the following major revisions to our initial proposal:
* **Refined Theme & Group Identity:** We pivoted our group name from *"CpU Later"* to *"Ca-Ching!"* and narrowed our topic scope. Instead of covering the entire CPU architecture and Fetch-Decode-Execute cycle, we are now laser-focused exclusively on **Cache Memory Mechanisms (Hits, Misses, and Locality)** to provide a much deeper, more educational dive.
* **Upgraded Interactive Element (No Static Slides):** We completely scrapped the basic calculator simulator. Our new interactive element is a **Dynamic CPU Cache Visualizer**. Users will actively input Hex memory addresses, and the system will compute the binary conversion, slice the bits (Tag, Index, Offset) in real-time, and animate the data routing.
* **Modernized Tech Stack:** To ensure the interactive element is highly animated and avoids feeling like a "static PowerPoint", we explicitly added **Framer Motion** and **ReactJS** to our Astro 6 / Node.js 26 framework to handle complex, real-time data-flow animations.

---

## Group Information
**Group Title:** Ca-Ching! (Group 5)
**GitHub Repository:** [CGCBRR/CSARCH2-virtual-exhibit-group5](https://github.com/CGCBRR/CSARCH2-virtual-exhibit-group5)

---

## Group Members

| Name                       | Role   |
| -------------------------- | ------ |
| Barreo, Carlo Gabriel      | Member |
| Eleydo, Renzel Vince       | Member |
| Gregorio, Gaibril Kyle     | Member |
| Leano, Jeremy              | Member |
| Rebudiao, Daniel Christian | Member |

---

## Topic Theme

**Caching! — How Cache Memory Works**

---

## I. The Core Concept: How Cache Memory Works

### 1. The Hardware Speed Gap and Cache Memory

**The Hardware Speed Gap**

CPUs have become incredibly fast, while main memory (RAM) has remained comparatively slow. Despite RAM being more affordable, its speed is a significant drawback. This creates a bottleneck where a fast processor constantly waits for data from slower RAM.

**Cache Memory**

Cache memory is a small, ultra-fast memory that sits directly on or adjacent to the CPU. It bridges the gap between RAM and the CPU by acting as a high-speed buffer that stores frequently accessed data — serving as a temporary storage area from which the processor can retrieve data efficiently.

> Cache memory operates approximately **10 to 100 times faster** than RAM and typically responds to a CPU request within a few nanoseconds.

---

### 2. Cache Hits vs. Cache Misses

**Cache Hit**

A cache hit occurs when the CPU requests data and finds it already stored in cache memory. Since cache is much faster than RAM, the CPU retrieves the data immediately — reducing latency and improving overall system performance.

**Cache Miss**

A cache miss occurs when the CPU requests data that is not present in the cache. The CPU must then check other memory levels (L2, L3 cache, or RAM) to retrieve the data, resulting in increased access time and reduced performance.

**How Cache Hits and Misses Work (Step-by-Step)**

1. **CPU requests data** — The processor first checks cache memory.
2. **Cache lookup** — If the requested data exists in cache, a *hit* occurs and the CPU immediately uses the data.
3. **Cache miss** — If the data is unavailable in cache, the CPU searches lower memory levels until the data is found.
4. **Cache update** — After retrieving the missing data, the CPU stores a copy in cache so future requests can be served faster.

---

### 3. Principle of Locality of Reference

The **Principle of Locality** describes the tendency of programs to repeatedly access the same data and instructions, or to access data located near recently accessed memory. Applying this principle in cache design significantly improves cache effectiveness. There are two main types:

**Temporal Locality (Locality in Time)**

If a memory location is accessed, it is likely to be accessed again soon. For example, in the loop below, the variable `total` is accessed repeatedly across iterations — keeping it in cache enables faster access each time:

```c
for (int i = 0; i < 1000; i++) {
    sum += total;
}
```

**Spatial Locality (Locality in Space)**

If a memory location is accessed, nearby memory locations are likely to be accessed soon as well. For example, the array traversal below accesses `arr[i]` sequentially — since array elements are stored contiguously in memory, loading one cache block often brings in nearby elements that will soon be needed:

```c
for (int i = 0; i < 1000; i++) {
    sum += arr[i];
}
```

---

## II. Tech Stack Plan

### 1. Proposed Interactive Element: CPU Cache Visualizer

Users simulate a CPU data request by typing a hexadecimal memory address. The visualizer then performs and displays the following steps:

**Address Breakdown**

- Converts the hex address to binary.
- Slices the binary bits into Tag, Index, and Offset fields.
- Animates lines or particle streams from each bit field to its corresponding location in the cache hardware.

**Cache Hit Visualization**

- Checks the calculated row index, confirms the valid bit is active, and verifies the address tag matches the stored tag.
- The targeted cache cell glows, the offset bits isolate the data, and a fast light-colored stream shoots back to the CPU with low-latency statistics displayed.

**Cache Miss Visualization**

- If the row is empty or tags do not match, a miss icon flashes and a slow gray data stream crawls down to RAM.
- RAM fetches a full memory block (exploiting spatial locality), overwrites the cache row metadata, and sends data back to the CPU with high-latency statistics displayed.

---

### 2. Technical Stack

To ensure seamless integration with the central virtual museum repository, the project strictly uses the following technologies:

| Layer          | Technology                                          |
| -------------- | --------------------------------------------------- |
| Core Framework | Node.js 26 + Astro 6 (via `astro.build` template) |
| Interactivity  | ReactJS components embedded in Astro `.mdx` pages |
| Styling        | TailwindCSS + ShadcnUI                              |
| Animations     | Framer Motion                                       |

Framer Motion handles complex visual transitions, including animated address calculations and data flow between the CPU, cache, and RAM.

---

## III. Style Guide

The exhibit uses a **Cyber-Physical Glassmorphism** design system built with Tailwind CSS and ShadcnUI, optimized for both desktop and mobile viewing.

| Element              | Specification                                             |
| -------------------- | --------------------------------------------------------- |
| Background           | Deep dark mode —`slate-950`                            |
| Cache Hit Indicator  | Vibrant green and cyan glowing borders                    |
| Cache Miss Indicator | Muted gray and amber tones                                |
| Typography           | Sans-serif (Inter or Geist) for high readability          |
| Desktop Layout       | Split-panel view — Simulator (left) / Visualizer (right) |
| Mobile Layout        | Single scrollable column via responsive grid              |

**Design Principles**

- High-contrast, glowing accents indicate data flow between the CPU and memory hierarchy.
- Clean educational typography is used for Exhibit Notes accordion sections.
- Responsive grid ensures the layout adapts gracefully across all screen sizes.

### Proposed Virtual Exhibit Design Layout

The following are high-fidelity UI snapshots of the proposed Cache Memory Visualizer:

**Desktop Views**

<img width="1090" height="591" alt="2" src="https://github.com/user-attachments/assets/c01a5f43-b57f-4ceb-8c19-b76b874f8e94" />
<img width="1087" height="584" alt="1" src="https://github.com/user-attachments/assets/3c3e3fa7-ef0a-4d06-8454-bb79edab9de7" />


**Mobile Views**

<img width="218" height="506" alt="3" src="https://github.com/user-attachments/assets/542968fb-e0d6-475a-bfe2-6e3209fb6a65" />
<img width="213" height="483" alt="4" src="https://github.com/user-attachments/assets/b3b1cfbb-2cb3-44f9-b50b-02c3adbfe648" />
<img width="238" height="510" alt="5" src="https://github.com/user-attachments/assets/620f7a40-147c-4d91-971c-8ec8ec16622a" />
<img width="244" height="516" alt="6" src="https://github.com/user-attachments/assets/404480bd-b70f-4c2a-9a64-1db789afc630" />

---

## IV. References

- *Cache Miss vs Cache Hit: What's the Difference?* (2023, May 10). WP Rocket. https://wp-rocket.me/wordpress-cache/cache-miss-vs-cache-hit/
- Lutkevich, B. (2024, June 25). *Cache memory*. Search Storage, TechTarget. https://www.techtarget.com/searchstorage/definition/cache-memory
