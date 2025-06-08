# Segment‑Tree C++ Library

A **generic**, **template‑based** C++ segment‑tree implementation supporting customizable range operations (sum/min/max etc) with **O(log N)** queries and updates. Automatically pads to the nearest power‑of‑two and robustly handles edge cases (empty/single‑element ranges). Ideal for **competitive programming** and algorithmic problem solving.

---

## Features

- **Template‑based** — works with any numeric or user‑defined type  
- **Customizable combine** — plug in your own function (sum, min, max, etc.)  
- **Dynamic sizing** — auto‑pads to power‑of‑two with neutral values  
- **Fast operations** — both updates and queries in **O(log N)**  
- **Edge‑case safe** — empty ranges and single elements handled gracefully  
- **Well‑documented** — inline comments, examples, and usage guide  

---

## Quick Start

### Prerequisites

- C++17‑compatible compiler (GCC ≥ 10, Clang ≥ 10, MSVC ≥ 2019)  

### Example

```cpp
#include "SegmentTree.h"

// combine for sum
int combineSum(int a, int b) { return a + b; }

int main() {
    std::vector<int> arr = {5, 3, 7, 1, 4};
    // initialize with neutral value 0
    SegmentTree<int> st(arr, 0, combineSum);

    // query sum on [1, 3] → 3 + 7 + 1 = 11
    int result = st.query(1, 3);

    // point update: arr[2] = 10
    st.update(2, 10);

    return 0;
}
